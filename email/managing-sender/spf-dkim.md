# SPF, DKIM 설정 이해하기

## 이 글에서는

이메일이 스팸으로 분류되는 확률을 낮추기 위해 필요한 SPF, DKIM 설정의 개념과 기본적인 설정 방법을 안내합니다.

스티비와 같은 이메일 마케팅 서비스를 사용할 때, 발신자 신뢰도가 충분히 확보되지 않으면 이메일이 스팸으로 분류되거나 전송이 차단될 수 있습니다. 이를 위한 대표적인 방법이 바로 SPF, DKIM 설정입니다.

***

{% hint style="info" %}
이 도움말은 SPF, DKIM 설정에 대한 개념을 이해하고, 설정이 필요한 상황을 판단할 수 있도록 돕기 위한 목적으로 작성되었습니다. 설정이 정상적으로 완료되었는지 확인하고 싶다면 [스티비 실험실](https://lab.stibee.com/)에서 바로 조회할 수 있습니다.
{% endhint %}

## 시작하기 전에 <a href="#h_01h9mgety1e8twf12twdq43z1x" id="h_01h9mgety1e8twf12twdq43z1x"></a>

SPF, DKIM 설정은 발신자 이메일 주소의 '도메인(URL)'에 적용하는 설정입니다. 예를 들어, 발신자 이메일 주소가 dooly@stibee.com이라면 stibee.com 도메인의 DNS 설정에 값을 추가해야 합니다.

따라서, 직접 소유한 도메인이 있는 경우에만 설정할 수 있으며, 공개 도메인(예. gmail.com, naver.com, kakao.com)이나 본인이 소유하지 않은 도메인에는 설정할 수 없습니다.

최근 [G메일](https://support.google.com/a/answer/81126?hl=ko\&ref=blog.stibee.com\&visit_id=638560892233199959-2361375663\&rd=1), [네이버 메일](https://notice.naver.com/notices/mail/15568)의 수신 정책이 강화되면서 SPF, DKIM 설정이 되어 있지 않은 발신자 주소로 발송한 이메일은 전송 속도가 느려지거나, 차단되거나, 스팸으로 표시될 수 있습니다. 장기적으로 이메일을 보낼 계획이라면, 도메인을 구입한 뒤 SPF, DKIM 설정을 완료하고 발송하는 것을 권장합니다.

도메인을 구입해서 발신자 이메일 주소를 생성하는 방법은 아래 도움말을 참고하세요.

{% content-ref url="../../getting-started/preparing-for-start/custom-sender-address.md" %}
[custom-sender-address.md](../../getting-started/preparing-for-start/custom-sender-address.md)
{% endcontent-ref %}



## SPF, DKIM이 뭔가요? <a href="#understand" id="understand"></a>

이메일 수신 서비스(예. G메일, 네이버 메일, 기업메일 등)에서 이메일 발신자가 신뢰할 만한 주소인지 '신뢰도'를 검증해 이메일 수신자에게 스팸 메일이 전달되는 것을 막기 위해 널리 사용되는 방법입니다.

* SPF: Sender Policy Framework
* DKIM: Domainkeys Identified Mail

<figure><img src="../../.gitbook/assets/SPF, DKIM.png" alt=""><figcaption></figcaption></figure>



스티비를 통해 이메일을 발송하면, 내가 직접 운영하는 서버가 아니라 스티비의 발송 서버를 통해 이메일이 전송됩니다. 이 경우 수신 서비스 입장에서는 "이 도메인의 이메일을 다른 서버가 대신 보내고 있네?" 라고 판단할 수 있습니다. 이로 인해, 수신 서비스 입장에서는 이메일을 의심스럽다고 볼 수 있는데요.

SPF, DKIM 설정은 수신 서비스에 "스티비 서버에서 보낸 이메일도 내가 보낸 게 맞다"는 것을 기술적으로 증명하는 역할을 합니다. 이를 통해 이메일이 스팸으로 분류될 확률을 낮출 수 있습니다.

이 과정을 "스티비의 SPF, DKIM 레코드를 우리 도메인에 추가한다."고 표현합니다.



## SPF, DKIM 설정은 왜 해야 하나요? <a href="#h_01h110pvcg49rkdv0eawp70p8r" id="h_01h110pvcg49rkdv0eawp70p8r"></a>

SPF, DKIM 설정을 하지 않아도 스티비에서 이메일을 발송할 수는 있습니다. 다만, 설정을 완료하면 다음과 같은 효과를 기대할 수 있습니다.

* 이메일이 '의심스러운 발신자'로 판단될 가능성이 낮아집니다.
* 이메일이 스팸으로 분류되거나 차단될 확률을 줄일 수 있습니다.
* G메일, 네이버 메일 등 주요 이메일 수신 서비스의 수신 정책을 충족할 수 있습니다.

특히 정당한 절차로 수신 동의를 받은 구독자에게 이메일을 보내고 있음에도 지속적으로 스팸으로 분류되는 문제가 발생한다면, 발신자 도메인에 SPF, DKIM 설정을 추가하는 것이 좋습니다.

<figure><img src="../../.gitbook/assets/image (35) (1).png" alt=""><figcaption></figcaption></figure>

_\* SPF, DKIM을 설정하지 않으면 구독자의 이메일 수신 서비스에서 이러한 경고 메시지가 표시될 수 있습니다._



## SPF, DKIM 설정하기 <a href="#h_01h110pzv84f02jnvmgmn7dvjx" id="h_01h110pzv84f02jnvmgmn7dvjx"></a>

{% hint style="info" %}
SPF, DKIM 설정은 도메인의 DNS 설정에서 진행합니다. 도메인 설정을 직접 수정할 수 없는 경우에는 내부의 도메인 관리자나 서버 관리자에게 이 도움말을 전달해 설정을 요청해 주세요.

아래 내용은 직접 설정을 진행하는 경우에 참고할 수 있는 가이드입니다.
{% endhint %}

### 내 도메인 관리 서비스 확인하기 <a href="#h_01h110q57sh5vs16d6dc4p5n5x" id="h_01h110q57sh5vs16d6dc4p5n5x"></a>

SPF, DKIM 설정은 도메인을 관리하는 서비스(네임서버가 등록된 곳)에서 진행합니다. 대부분의 경우 도메인을 처음 구입한 업체에서 관리하고 있습니다.

도메인 관리 서비스를 확인하기 어렵다면, [후이즈 조회 서비스](https://xn--c79as89aj0e29b77z.xn--3e0b707e/kor/whois/whois.jsp)를 통해 도메인을 검색한 뒤 'name server' 항목에 표시된 정보를 확인해 주세요.



### 발신자 이메일 주소 도메인의 DNS 관리 화면으로 이동하기 <a href="#h_01hq81x80tf4sr4nxya5z9bra0" id="h_01hq81x80tf4sr4nxya5z9bra0"></a>

도메인 관리 서비스를 확인했다면, 'DNS 관리' 또는 '도메인 관리' 화면으로 이동합니다.

아래는 자주 사용되는 도메인 관리 서비스별 설정 안내입니다. 목록에 없는 서비스를 사용 중이라면, 각 서비스의 고객센터를 통해 안내받을 수 있습니다.

* 카페24
  * SPF: [TXT 레코드 설정 (SPF 관리)](https://help.cafe24.com/faq/domain/dns-management/connect-domain-to-external-hosting-mail/#-txt-%EA%B4%80%EB%A6%AC)
  * DKIM: [CNAME 레코드 설정 (별칭 관리)](https://help.cafe24.com/faq/domain/dns-management/connect-domain-to-external-hosting-mail/#-%EB%B3%84%EC%B9%ADcname-%EA%B4%80%EB%A6%AC)
* 후이즈:&#x20;
  * SPF: [SPF(TXT) 값은 어떻게 설정하나요?](http://cs.whois.co.kr/faq/?p=list\&service=1\&category=\&keyfield=subject\&keyword=SPF)
  * DKIM: [CNAME 레코드 설정하는 방법을 알려주세요.](http://cs.whois.co.kr/faq/?p=list\&service=1\&category=\&keyfield=content\&keyword=CNAME)&#x20;
* 가비아: [DNS 레코드 설정하기](https://customer.gabia.com/manual#/domain/287/1201)
* 구글 도메인: [리소스 레코드](https://support.google.com/domains/answer/3290350?hl=ko\&ref_topic=9018335)
  * 구글 도메인에서 도메인을 구입하고 이 도메인에 구글 워크스페이스를 함께 사용하는 경우에는 DNS 설정을 수정할 때 주의해야 할 점이 있습니다. 자세한 내용은 [여기](../questions.md#google-domain-google-workspace)를 참고하세요.



### SPF, DKIM 설정을 위한 값을 추가 <a href="#h_01h110r106ca5d9t7kcdg00hgm" id="h_01h110r106ca5d9t7kcdg00hgm"></a>

이제 발신자 이메일 주소의 도메인 DNS 설정에 스티비의 SPF, DKIM 값을 추가합니다. 직접 설정이 어렵다면 도메인 관리자나 서버 관리자에게 설정을 요청해 주세요.

#### SPF 설정

SPF는 TXT 레코드에 값을 추가합니다.

#### **도메인에 기존에 설정된 TXT 값이 없는 경우**

* 이름(호스트, 별칭): @ 또는 비워둠
* TTL(수명): 3600 또는 기본값
* 값(응답, 대상): v=spf1 include:mail.stibee.com \~all

#### **도메인에 이미 설정한 TXT 레코드가 존재하는 경우**

새 레코드를 추가하지 않고, 기존 값에 스티비 SPF 값을 함께 입력합니다. 예를 들어, 도메인에 이미 아래와 같은 형식의 값이 입력되어 있다고 한다면,

* v=spf1 include:sub.domain.com \~all

기존 값에 include 문을 사용하여 스티비의 SPF 값을 하나로 합쳐 입력하면 됩니다.&#x20;

* 예. v=spf1 include:sub.domain.com **include:mail.stibee.com** \~all



#### **DKIM**

DKIM은 CNAME 레코드에 값을 추가합니다.

* 이름(호스트): stb.\_domainkey.yourdomain.com 또는 stb.\_domainkey
* 값: dkim.stibee.com

이름(호스트, 별칭)의 yourdomain.com은 발신자 이메일 주소의 도메인으로 변경합니다. 예를 들어, 발신자 이메일 주소가 hello@stibee.com이라면, stb.\_domainkey.stibee.com 또는 stb.\_domainkey 입력합니다. stb.\_domainkey는 도메인과 상관없는 고정된 값입니다.

_\* 이름이나 값의 입력 형식은 사용 중인 도메인 관리 서비스에 따라 달라질 수 있습니다. 이 경우는 사용하는 서비스의 고객센터로 문의하시면 그에 맞는 형식을 안내받을 수 있습니다._



#### **설정 확인하기**

설정이 정상적으로 완료되었는지 여부는 [스티비 실험실](https://lab.stibee.com/)에서 도메인을 검색해 바로 확인할 수 있습니다. 또는 \[주소록 → 대시보드 → 발신자 이메일 주소]에서도 확인할 수 있습니다. 서버 상황에 따라 설정이 완료되기까지 최대 48시간이 소요될 수 있습니다.

DNS 설정 특성상 반영까지 최대 48시간이 소요될 수 있습니다. 즉시 확인되지 않는 경우, 잠시 후 다시 상태를 조회해 주세요.&#x20;

만약, 48시간 이후에도 설정값이 조회되지 않는다면 이메일(support@stibee.com) 또는 채팅 문의(로그인 후 화면 오른쪽 아래 물음표 버튼)를 통해 문의해 주세요.

<figure><img src="../../.gitbook/assets/스티비 실험실.png" alt=""><figcaption></figcaption></figure>
