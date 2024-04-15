---
layout:
  title:
    visible: true
  description:
    visible: false
  tableOfContents:
    visible: true
  outline:
    visible: true
  pagination:
    visible: true
---

# DMARC 설정 이해하기

## 이 글에서는 <a href="#h_01hkkxxnv9dqk9fszaqcgkqegf" id="h_01hkkxxnv9dqk9fszaqcgkqegf"></a>

DMARC 설정은 SPF, DKIM 설정과 더불어 수신 서비스에서 이메일의 스팸 여부를 판단하기 위해 가장 대표적으로 사용하는 설정입니다. DMARC 설정에 대해 알아봅니다.

***

## 시작하기 전에 <a href="#h_01hj2kjaaxkfp0rtbg4tz89b5g" id="h_01hj2kjaaxkfp0rtbg4tz89b5g"></a>

2024년 2월부터 G메일의 강화된 대량 메일 발송 가이드라인이 적용될 예정입니다. 가이드에 따르면 5,000건 이상의 이메일을 G메일 수신자에게 보낼 때 DMARC 정책이 설정하지 않으면 G메일에서 전송 속도가 제한되거나 차단되거나 스팸으로 표시될 수 있습니다.

DMARC 설정은 발신자 주소의 도메인에 하는 설정입니다. 예를 들어 사용하는 발신자 이메일 주소가 dooly@stibee.com이라면 예시 주소의 도메인에 해당하는 stibee.com에 추가하는 설정입니다. 따라서 직접 가지고 있는 도메인에만 설정이 가능하며 공개된 이메일 주소(예: naver.com, gmail.com, kakao.com 등) 또는 본인이 가지고 있지 않은 도메인(예: stibee.com)에는 설정이 불가능합니다.

가지고 있는 도메인이 없다면 아래 도움말을 참고해 나만의 발신자 이메일 주소를 만들어보세요.\
[나만의 발신자 주소를 만들고 싶어요](../../getting-started/prepare-for-start/custom-sender-address.md)

DMARC 설정을 위해서는 도메인에 미리 스티비의 SPF, DKIM 설정을 추가해야 합니다. SPF, DKIM 설정을 한 뒤 최소 48시간이 지난 뒤 DMARC 설정을 시도하시기를 바랍니다. SPF, DKIM 설정을 하는 방법은 [SPF, DKIM 설정 이해하기](dmarc.md#h\_01hkkyss98y0fzps03mx9zjhy2)를 참고해 주세요.

\* _이 도움말은 DMARC 설정에 대한 개념을 설명하기 위한 목적으로 작성됐습니다. 설정이 잘 완료됐는지 조회하고 싶은 경우에는_ [_스티비 실험실_](https://lab.stibee.com/)_에서 바로 확인할 수 있습니다._



## DMARC가 뭔가요? <a href="#h_01hm827fnmxzqf0qdngf700cd6" id="h_01hm827fnmxzqf0qdngf700cd6"></a>

DMARC는 Domain-based Message Authentication, Reporting & Conformance의 약자로 누군가 내 발신자 이메일 주소를 도용해 발송하는 것을 방지하기 위해 널리 사용되는 이메일 처리 방식입니다. DMARC를 설정함으로써 누군가 내 발신자 이메일 주소와 똑같은 가짜 발신자 주소를 사용해서 스팸 메일을 보내 피해가 발생하는 것을 방지할 수 있습니다. DMARC 설정은 이메일을 보내는 사람과 받아보는 사람을 모두 보호하기 위한 효과적인 장치입니다.



## DMARC 설정은 왜 해야 하나요? <a href="#h_01hm827xqzg5s0fq9n4s69d37q" id="h_01hm827xqzg5s0fq9n4s69d37q"></a>

많은 이메일 수신 서비스(예: G메일, 네이버 메일, 야후 메일 등)에서는 수신자를 보호하기 위해 이메일을 받아볼 때 도메인의 [SPF, DKIM 설정](https://help.stibee.com/hc/ko/articles/4756529633423) 뿐 아니라 DMARC 설정도 참고합니다. DMARC 정책을 설정해 도메인을 사칭하여 스팸 메일을 보내는 것을 막을 수 있고, 결과적으로 내 도메인의 평판도 올라갑니다.

\*_도메인 평판은 수신 서비스에서 스팸 메일 여부를 판단하는 주요 기준 중 하나입니다. 이메일이 스팸으로 분류되지 않도록 하려면 높은 도메인 평판을 유지해야 합니다._

DMARC 정책이 설정된 발신자 주소가 보내는 이메일은 상대적으로 안전한 이메일일 확률이 높기 때문에 이메일 수신 서비스에서도 DMARC가 설정된 도메인의 이메일을 더 선호합니다.



## DMARC는 어떻게 동작하나요? <a href="#id-01hm8545cxxx7abbjjx8s40x92" id="id-01hm8545cxxx7abbjjx8s40x92"></a>

DMARC 설정은 내가 보낸 이메일의 발신자 주소 신뢰도를 검증한 결과에 따라 어떻게 처리하면 좋을지 구체적인 가이드를 수신 측에게 제공합니다. 스티비와 같은 이메일 마케팅 서비스를 사용해 이메일을 보내면, 내가 가지고 있는 발송 서버가 아닌 사용하는 서비스에서 가지고 있는 서버로 발송이 이루어집니다. 따라서 내가 가지고 있는 서버가 아닌 다른 곳에서 내 발신자 주소를 사용해 이메일을 보내고 있다면 수신 서비스 쪽에서는 이 이메일을 의심스럽다고 판단할 수 있습니다.

여기서 “스티비에서 보낸 것도 내가 보낸 것이 맞다.”를 표시하는 건 SPF, DKIM 설정입니다. SPF, DKIM 값을 검사한 결과 의심스러운 이메일이라고 판단한다면 수신 쪽에서는 이 이메일을 어떻게 처리할지 내부 정책에 따라 판단합니다. 이때 DMARC 정책은 수신 쪽에 “내 도메인에서 보낸 이메일이 신뢰도에 문제가 있다면 스팸으로 처리하라.” 와 같은 구체적인 지침을 전달하는 것으로, 수신 쪽에서는 이 지침에 따라 이메일을 처리합니다.

예를 들어, example.com이라는 도메인에 스티비의 SPF, DKIM 값이 등록되어 있고 DMARC 정책을 신뢰도가 의심되는 경우 스팸으로 표시하라는 정책을 운영한다고 가정하면,

* dooly@example.com 발신자 주소를 사용해 스티비로 이메일을 gildong.go@mail.com에게 보냈다면 신뢰도 설정을 통과해 이메일이 정상적으로 받은 메일함으로 도착합니다.
* dooly@example.com 발신자 주소를 사용해 스티비가 아닌 다른 A 서비스를 사용해 이메일을 gildong.go@mail.com에게 보냈다면 신뢰도 설정을 통과하지 못해 이메일이 DMARC 정책에 따라 스팸으로 표시됩니다.



## DMARC 설정하기 <a href="#h_01hj5fn6r44fg750r172j5pwhn" id="h_01hj5fn6r44fg750r172j5pwhn"></a>

{% hint style="info" %}
DMARC설정은 도메인에 해야 하는 설정입니다. 따라서 도메인 설정을 직접 수정하실 수 없는 경우라면 내부 도메인, 서버 관리자에게 이 도움말 내용을 전달하여 설정을 요청해 주세요. 아래 내용은 기술적인 실제 설정 값에 대한 설명이므로 내부 담당자에게 전달하거나 직접 설정하는 경우 참고하실 수 있습니다.
{% endhint %}

### 내 도메인 관리 서비스 확인하기 <a href="#h_01hkkxxnvahbdjattw3vk8ycr8" id="h_01hkkxxnvahbdjattw3vk8ycr8"></a>

DMARC 설정은 내 도메인을 관리하는 서비스(네임서버가 등록된 곳)에서 설정할 수 있습니다. 도메인의 네임서버가 등록된 곳은 상황에 따라 다르지만 보통 처음 도메인을 구입한 곳에 등록되어 있을 확률이 높습니다. 자세한 내용은 도메인을 구입한 곳의 고객센터를 통해 문의하시면 안내받으실 수 있습니다.&#x20;

[_후이즈 도메인 조회_](https://xn--c79as89aj0e29b77z.xn--3e0b707e/kor/whois/whois.jsp)_에서 직접 확인하는 것도 가능합니다. 검색창에 도메인을 입력하고 결과에 'name server' 부분에 입력된 링크가 내 도메인의 네임서버가 등록된 곳입니다._



### 발신자 이메일 주소 도메인의 DNS 관리 화면으로 이동하기 <a href="#h_01hkkxzep6gtg8knkm5z11dz0s" id="h_01hkkxzep6gtg8knkm5z11dz0s"></a>

네임서버가 설치된 내 도메인 관리 서비스를 확인했다면 다음은 관리 서비스의 'DNS 관리' 화면으로 이동해 설정을 해주면 됩니다. 도메인 관리 서비스마다 경로가 다르지만 일반적으로 '도메인 관리' 또는 'DNS 관리' 등의 화면을 찾으시면 됩니다. 아래 서비스를 사용하고 있다면 링크된 각 도움말을 참고해 주세요. 아래 업체가 아닌 다른 업체에서 서비스를 사용하고 있다면 그 서비스의 고객센터로 문의하면 자세하게 안내받을 수 있습니다.

* **카페24**
  * [카페24 도메인 DNS 레코드 설정은 어떻게 하나요?](https://help.cafe24.com/cs/cs\_faq\_view.php?idx=3766) 4. TXT 레코드 추가
* **가비아**
  * SPF 설정 방법: [DNS 레코드 설정하기](https://customer.gabia.com/manual#/domain/287/1201) 4) TXT 레코드 설정하기 (SPF 레코드)
* **후이즈**
  * SPF 설정 방법: [SPF(TXT) 값은 어떻게 설정하나요?](http://cs.whois.co.kr/faq/?p=list\&service=1\&category=\&keyfield=subject\&keyword=SPF)
* **구글 도메인**
  * [리소스 레코드](https://support.google.com/domains/answer/3290350?hl=ko\&ref\_topic=9018335)

_\*구글 도메인에서 도메인을 구입하고 이 도메인에 구글 워크스페이스를 함께 사용하는 경우에는 DNS 설정을 수정할 때 주의해야 할 점이 있습니다. 자세한 내용은_ [_여기_](../questions.md#google-domain-google-workspace)_를 참고하세요._



### SPF, DKIM 설정하기 <a href="#h_01hkkyss98y0fzps03mx9zjhy2" id="h_01hkkyss98y0fzps03mx9zjhy2"></a>

DMARC 설정을 하기 위해서는 SPF, DKIM 설정을 먼저 해야 합니다. 일반적으로 SPF, DKIM 설정이 적용되기까지 48시간이 소요되기 때문에 SPF, DKIM 설정을 추가한 뒤 최소 48시간 뒤에 DMARC 설정을 추가하는 것이 좋습니다.

SPF, DKIM을 설정하는 방법은 [SPF, DKIM 설정 이해하기](spf-dkim.md)를 참고해 주세요.



### DMARC 설정을 위한 TXT 레코드 추가 <a href="#h_01hkky31a2vkzarwpz76500yra" id="h_01hkky31a2vkzarwpz76500yra"></a>

SPF, DKIM 값을 추가했고 48시간이 지났다면 도메인의 설정 값에 DMARC 값을 추가하면 됩니다. DMARC 값은 TXT 레코드를 추가하고 설정 값을 입력하면 됩니다. DMARC 레코드에는 여러 태그 값이 존재합니다. 태그 값은 상황에 따라 수정하여 작성하시면 좋지만, 처음부터 많은 설정을 추가하는 경우 이메일 발송에 문제가 생길 수 있습니다.&#x20;

여기 가이드에서는 가장 처음에 DMARC 설정을 추가할 때 시작하면 좋은 설정 값에 대해 안내하고 있으며 다른 태그 값을 어떻게 설정할지는 이메일을 발송한 뒤 모니터링을 진행하며 조금씩 수정하는 것을 권장합니다.

다시 도메인의 DNS 설정 화면으로 이동하여 TXT 레코드에 아래의 값을 추가합니다.&#x20;

* 이름(레코드명): \_dmarc 또는 \_dmarc.yourdomain.com
* 값: v=DMARC1; p=none;

p 태그의 값을 none, quarantine, reject 등으로 설정함으로써 수신 서비스에 SPF, DKIM이 설정되지 않은 이메일을 어떻게 처리할지 지침 수준을 전달할 수 있습니다. 처음부터 SPF, DKIM 설정이 되어 있지 않은 경우 이메일 수신을 거부하는 가장 높은 조치인 reject로 설정하는 경우 원인 파악이 어려울 뿐 아니라 이메일 수신에 문제가 발생할 수 있으니 가장 낮은 단계의 조치인 none을 기준으로 설정하고 발송을 테스트해 보며 처리 수준을 올리는 것을 권장합니다.



### DMARC 설정 확인 방법 <a href="#id-01hna6g3r3swgg962vng8sckc3" id="id-01hna6g3r3swgg962vng8sckc3"></a>

설정 값이 정상적으로 추가됐는지 여부는 [스티비 실험실](https://lab.stibee.com/)에서 설정한 도메인을 검색창에 입력하면 간단하게 조회할 수 있습니다. 또는 주소록 대시보드 \[발신자 이메일 주소]에서도 확인할 수 있습니다. 서버 상황에 따라 설정이 완료되기까지 최대 48시간이 소요될 수 있습니다.&#x20;

설정 여부가 바로 확인이 되지 않는다면 조금 기다린 후 다시 상태를 조회해 주세요. 만약, 48시간 이후에도 설정 값이 조회가 되지 않는다면 이메일(support@stibee.com) 또는 채팅 문의(로그인 후 화면 오른쪽 아래 물음표 버튼)를 통해 문의해 주세요.



## 참고. DMARC 레코드 태그 종류 <a href="#h_01hkkyss986cfgztq2e0jxpc5c" id="h_01hkkyss986cfgztq2e0jxpc5c"></a>

여기까지만 설정해도 이메일 발송은 문제없이 진행할 수 있습니다. 다만 DMARC 설정은 여러 가지 추가 정책을 수행할 수 있는 여러 태그를 제공하고 있습니다. 태그 설정 값에 정해진 답은 없습니다. 내부적으로 운영하는 정책에 따라 이 태그 값을 수정하거나 추가해 주시면 됩니다.&#x20;

DMARC 레코드 태그 값 중 v와 p태그만 필수 설정이고 나머지는 모두 선택사항입니다.

_\*각 태그 값은 세미콜론(;)을 구분자로 사용합니다. 여러 태그를 설정하는 경우 세미콜론으로 각 태그를 구분해서 사용하면 됩니다._

| 태그                        | 설정 값                                                                                                     |
| ------------------------- | -------------------------------------------------------------------------------------------------------- |
| [v](broken-reference)     | V=DMARC1, 필수 설정 값입니다.                                                                                    |
| [p](broken-reference)     | p=none 또는 p=quarantine 또는 p=reject, 필수 설정 값입니다.                                                          |
| [pct](broken-reference)   | <p>pct=’1부터 100 사이의 정수’<br>작성 예시) pct=50 (보내는 이메일의 50%에만 DMARC 정책을 적용하라.), 선택 설정 값입니다.</p>               |
| [rua](broken-reference)   | <p>rua=mailto:’DMARC 활동 보고서를 받아볼 이메일 주소’<br>작성 예시) rua=mailto:dmarc-reports@example.com, 선택 설정 값입니다.</p> |
| [sp](broken-reference)    | p=none 또는 p=quarantine 또는 p=reject, 선택 설정 값입니다.                                                          |
| [adkim](broken-reference) | adkim=r 또는 adkim=s, 선택 설정 값입니다.                                                                          |
| [aspf](broken-reference)  | aspf=r 또는 aspf=s, 선택 설정 값입니다.                                                                            |

### **V=DMARC1** <a href="#h_01hkxsq091481navbc79d5txpf" id="h_01hkxsq091481navbc79d5txpf"></a>

DMARC의 버전을 설명하는 태그입니다. 이 태그는 '필수' 항목이며, DMARC1로 설정해야 합니다. DMARC 레코드는 다양한 태그를 포함할 수 있습니다. 그중 V 태그는 반드시 모든 태그 중 가장 앞에 작성해야 합니다.

### **p=none, p=quarantine, p=reject** <a href="#h_01hkxsq091309xz9k2az6a8w4x" id="h_01hkxsq091309xz9k2az6a8w4x"></a>

발신자 주소에 설정된 도메인이 SPF, DKIM 설정이 되어 있지 않은 경우 이 이메일을 어떻게 조치할지에 대한 내용을 이메일 수신 서비스에 전달합니다.

* none: 아무런 조치도 하지 않습니다.
* quarantine: 이메일을 스팸으로 표시하고 스팸함으로 보냅니다.
* reject: 이메일의 수신을 거부합니다. 스팸함에도 도착하지 않습니다.

이 태그는 v 태그와 같이 필수로 설정해야 하는 항목입니다. 처음에는 none으로 설정해 모니터링을 진행하고 문제가 없다면 quarnatine, reject 순서로 점점 조치를 강화하는 것을 일반적으로 권장하고 있습니다.

### **pct=** <a href="#h_01hkxsq091t8799hmv0cev37dw" id="h_01hkxsq091t8799hmv0cev37dw"></a>

이메일 중 DMARC 정책을 적용할 비율을 정합니다. 값은 1에서 100 사이의 정수로 설정하면 됩니다. pct 값을 설정하지 않으면 기본값은 100으로 설정되고 발송하는 모든 이메일(100%)에 DMARC 정책이 적용됩니다.

일반적으로 처음에는 pct=5 정도로 낮은 값을 설정해 모니터링을 진행한 뒤 점점 비율을 늘려 최종적으로는 pct=100의 값으로 설정하는 것이 권장됩니다.

### **rua=mailto:** <a href="#h_01hkxsq0916j0k6c3329rb7b85" id="h_01hkxsq0916j0k6c3329rb7b85"></a>

DMARC 정책 적용 결과에 대한 보고서를 수신할 이메일 주소를 입력합니다. DMARC 설정이 적용되면 이메일을 받아본 수신 서비스들에서는 정책의 적용 결과를 보고서로 작성해 이메일로 회신합니다. 보고서를 분석하면 내 발신자 주소의 이메일이 어떻게 처리되고 있는지 결과를 확인할 수 있습니다.

단, 이 옵션을 설정하는 경우 매우 많은 양의 이메일 보고서가 전달될 수 있기 때문에 DMARC 보고서를 전용으로 받아볼 이메일 주소를 설정하는 것을 권장합니다.

설정은 이메일 주소에 mailto: 를 포함해서 설정하면 됩니다.

* 예) mailto:dmarc-report@example.com

DMARC 보고서를 여러 이메일에서 받아보고 싶다면 각 이메일 주소를 쉼표로 구분하고 개별 주소 앞에 mailto: 를 추가합니다.

* 예) mailto:dmarc-report-1@example.com, mailto:dmarc-report-2@example.com

### **sp=** <a href="#h_01hkxsq091d8km2tep60szfnrr" id="h_01hkxsq091d8km2tep60szfnrr"></a>

하나의 도메인에 여러 하위 도메인을 사용하는 경우가 있습니다. 하위 도메인에서 발송된 이메일에는 상위 도메인과 다른 DMARC 정책을 적용하고 싶은 경우 이 옵션을 사용하면 됩니다. 위에서 설정한 p 태그와 같은 역할과 설정 값을 가지지만 sp 태그는 상위 도메인이 아닌 하위 도메인에만 별도로 적용된다는 것에서 차이점을 가집니다. 예를 들어 example.com에 대한 설정을 p=reject, sp=none으로 설정했다면

* 발신자 주소가 mail@example.com으로 발송된 경우 이메일이 SPF, DKIM 설정을 통과하지 못했을 때 모든 이메일의 수신이 거부(reject)됩니다.
* 발신자 주소가 \[mail@test.example.com]\(mailto:mail@test.example.com%EB%A1%9C)로 발송된 경우 이메일이 SPF, DKIM 설정을 통과하지 못했다고 하더라도 DMARC 정책을 적용하지 않습니다. (none)

설정값은 아래와 같습니다.

* none: 아무런 조치를 취하지 않습니다.
* quarantine: 이메일을 스팸으로 표시하고 스팸함으로 보냅니다.
* reject: 이메일의 수신을 거부합니다. 스팸함에도 도착하지 않습니다.

### **adkim=** <a href="#h_01hkxsq091rrf0x7fnrtchstgy" id="h_01hkxsq091rrf0x7fnrtchstgy"></a>

발신자 주소에 설정한 DKIM 설정값이 발송된 이메일에 포함된 DKIM 서명과 어느 정도 일치해야 DMARC 정책을 통과했다고 판단할지 여부를 정의합니다. DKIM 서명은 일반 사용 환경에서는 확인할 수 없고 '이메일 원본'의 헤더 값에서 확인할 수 있습니다.

스티비로 이메일을 보내면서 정상적으로 스티비의 DKIM 값을 추가했다면 일반적으로 설정을 통과하는 데 문제는 없습니다.

* s: DKIM을 설정한 도메인과 이메일을 발신한 도메인이 완전히 일치하는 경우에만 이메일 발송을 허용합니다. 예를 들어 example.com 도메인에 DKIM을 설정한 경우 반드시 발신자 도메인은 example.com인 경우에만 발송을 허용합니다. 서브 도메인으로 설정해 발송한 경우에는 두 도메인이 완전히 일치하지 않기 때문에 이메일 발송을 허용하지 않습니다.
  * hello@example.com으로 발신자 주소를 설정한 경우 발송이 허용됨
  * hello@sub.example.com으로 발신자 주소를 설정한 경우 발송을 허용하지 않음
* r: DKIM을 설정한 도메인과 이메일을 발신한 도메인이 부분적으로 일치하는 경우에도 이메일 발송을 허용합니다. 예를 들어 example.com 도메인에 DKIM을 설정한 경우 example.com의 서브 도메인으로 설정된 발신자 이메일 주소도 발송을 허용합니다.
  * hello@example.com으로 발신자 주소를 설정한 경우 발송이 허용됨
  * hello@sub.example.com으로 발신자 주소를 설정해도 발송이 허용됨

adkim 값은 설정하지 않으면 기본적으로 r 값으로 설정됩니다. 가능하면 adkim 설정은 기본값인 r 값을 유지하는 것을 권장합니다. 이 태그는 '선택사항'입니다.

### **aspf=** <a href="#h_01hkxsq091n6f7nh82dj16kt2q" id="h_01hkxsq091n6f7nh82dj16kt2q"></a>

발신자 주소에 설정한 SPF 설정값이 발송된 이메일에 포함된 SPF 서명과 어느 정도 일치해야 DMARC 정책을 통과했다고 판단할지 여부를 정의합니다. SPF 서명은 DKIM과 마찬가지로 일반 사용 환경에서는 확인할 수 없고 '이메일 원본'의 헤더 값에서 확인할 수 있습니다.

* s: MAIL FROM의 도메인과 발신자 주소의 도메인이 완전히 일치해야 발송을 허용합니다.
* r: MAIL FROM의 도메인과 발신자 주소의 도메인이 부분적으로 일치해도 발송을 허용합니다.

aspf 값은 설정하지 않으면 기본적으로 r 값으로 설정됩니다. 가능하면 aspf 설정은 기본값인 r 값을 유지하는 것을 권장합니다.

