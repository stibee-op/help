# 이메일 스팸 표시 방지하기

## 언제 필요한가요? <a href="#h_01hkm26fsyrr8kbfdtmncznw7h" id="h_01hkm26fsyrr8kbfdtmncznw7h"></a>

* 보낸 이메일이 스팸으로 분류되거나 메일함에 도착하지 않는 경우
* 스팸으로 분류되는 비율이 높아 비율을 낮추고 싶은 경우

***

내가 보낸 이메일이 때때로 스팸으로 표시되거나 수신이 차단될 수 있습니다. 스팸으로 표시되는 것을 막기 위해서는 이메일이 스팸으로 표시되는 원리를 이해하고, 적절한 조치를 진행해야 합니다.



## 스팸으로 표시되는 이유

스팸 표시는 이메일 수신 서비스에서(예: gmail.com, naver.com 등) 자신들의 정책에 따라 결정합니다. 이메일 수신 서비스에서는 사용자(구독자)에게 스팸 메일이 전달되어 발생하는 피해를 막기 위해 여러 안전장치를 설치합니다. 수신되는 이메일들을 모두 저마다의 기준에 따라 검사하고, 정상적으로 메일함에 보낼지 아니면 스팸으로 표시할지 또는 차단할지 여부를 결정합니다. 검사 기준은 서비스마다 다양하지만, 일반적으로 아래 기준에 따라 스팸 메일 여부를 판단합니다.



### 발신자 이메일 주소의 신뢰도, 평판 <a href="#h_01hkxtbqn0k3y4wtwe9tec6k43" id="h_01hkxtbqn0k3y4wtwe9tec6k43"></a>

이메일 수신 서비스는 이메일을 보내는 사람과 출처가 믿을만하다면 안전한 이메일일 확률이 높다고 판단합니다. 반대로 신뢰할 수 없는 사람과 출처에서 발송되는 이메일은 수신자에게 위험한 내용을 담은 스팸 메일일 가능성이 높다고 판단합니다.



### 이메일의 제목, 내용 <a href="#h_01hkxtbqn0nqvvxqs57xb7fmv0" id="h_01hkxtbqn0nqvvxqs57xb7fmv0"></a>

이메일 수신 서비스에서는 이메일의 제목 또는 내용이 수신자에게 전달되기 적절한 내용인지 여부를 평가합니다. 내용의 적절성 여부는 전반적인 이메일 내용이기도 하지만 수신자(구독자)가 이메일에 어떻게 반응하는지 여부도 종합적으로 판단합니다. 수신자(구독자)가 이메일을 자주 열어보지 않는다면 이메일 수신 서비스에서는 앞으로 내 이메일을 스팸으로 표시할 가능성이 높습니다.



## 스팸으로 분류되지 않도록 조치하기 <a href="#h_01hkxtbqn03avqyp8chnpma30f" id="h_01hkxtbqn03avqyp8chnpma30f"></a>

### 관리적인 조치 <a href="#h_01hkxtbqn0m0hxne1yy4k4pbpr" id="h_01hkxtbqn0m0hxne1yy4k4pbpr"></a>

#### gmail.com, naver.com을 발신자 주소 도메인으로 사용하지 않기 <a href="#h_01hky4f9q1as1161dm4a4cv19y" id="h_01hky4f9q1as1161dm4a4cv19y"></a>

[G메일](https://support.google.com/a/answer/81126?hl=ko\&visit_id=638560892231409319-2480877127\&rd=1)과 [네이버 메일](https://notice.naver.com/notices/mail/15568)의 강화된 이메일 발신자 가이드라인에 따르면, 외부의 다른 서비스를 사용해서 이메일을 보내는 경우 gmail.com, naver.com 도메인을 사용할 수 없습니다. 만약, 외부의 다른 서비스를 사용해 이메일을 보낼 때 gmail.com이나 naver.com을 사용하는 경우 이메일이 스팸으로 표시되거나 차단될 수 있습니다. 따라서, 발신자 주소는 gmail.com, naver.com이 아닌 다른 도메인을 사용하는 주소로 변경해 사용하는 것이 좋습니다.

스티비에서는 gmail.com, naver.com 도메인으로 만든 이메일은 발신자 이메일 주소로 설정할 수 없으며, 스티비에서 제공하는 send.stibee.com 도메인으로 자동 변경되어 저장됩니다. 도메인 변경은 무료이며, 별도의 과금이 이루어지지 않습니다. (예: dooly@gmail.com -> dooly-gmail.com@send.stibee.com)

가능하다면 공개된 도메인(예: hanmail.net 등)이 아닌 내 도메인을 사용하는 발신자 주소를 만들어 사용하는 것을 권장합니다. 나만의 발신자 주소를 만드는 법이 궁금하다면 아래 도움말을 참고해 보세요.

{% content-ref url="../getting-started/preparing-for-start/custom-sender-address.md" %}
[custom-sender-address.md](../getting-started/preparing-for-start/custom-sender-address.md)
{% endcontent-ref %}



#### 수신 동의를 받은 구독자에게만 이메일 발송하기 <a href="#h_01hkxtbqn06peebadmh04jfw72" id="h_01hkxtbqn06peebadmh04jfw72"></a>

정보통신망법에서는 광고성 정보를 전송하는 경우 절차에 따라 수신 동의를 받은 경우에만 이메일을 발송할 수 있다고 규정하고 있습니다. 따라서, 수신 동의를 받지 않고 발송된 이메일을 이메일 수신 서비스에서는 스팸 메일로 판단할 가능성이 높습니다.

수신 동의를 받지 않은 것으로 의심되는 경우 이메일은 스팸으로 표시될 가능성이 높고, 스팸으로 표시되는 비율이 늘어나면 발신자 이메일 주소의 평판이 떨어져 다른 정상적인 구독자의 이메일 수신에도 영향이 발생할 수 있습니다.

그리고 수신 동의를 받지 않은 구독자에게 발송하는 경우 이메일을 받아본 구독자가 원해서 받아본 것이 아닐 가능성이 높아 이메일을 보낸 발신자 이메일 주소를 ‘스팸 신고’할 가능성도 높습니다. 스팸 신고가 쌓이면 발신자 이메일 주소의 평판이 떨어져 전반적인 이메일 발송에 영향이 발생할 수 있습니다. 따라서 이메일은 수신 동의를 받은 구독자에게만 발송하는 것이 좋습니다.



#### 주기적으로 이메일에 반응이 없거나 발송에 실패하는 구독자 명단 정제하기

구독자가 이메일을 오랫동안 열어보지 않는 경우에도 스팸으로 표시될 수 있습니다. 일정 기간 꾸준하게 이메일을 보냈지만, 오픈 기록이 존재하지 않는 구독자는 주기적으로 확인하여 명단을 정제하여 이메일이 스팸으로 표시되는 비율을 낮추는 것이 중요합니다.

마찬가지로 꾸준히 발송에 실패하는 구독자에게 계속 이메일을 보낸다면 발신자 이메일 주소 평판이 떨어질 수 있습니다. 따라서 계속해서 발송에 실패하는 구독자도 주기적으로 확인해 명단에서 삭제하는 것을 권장합니다.

정리하면 스팸으로 분류되는 것을 피하고자주기적으로 이메일을 열어보지 않거나 발송에 실패하는 구독자는 명단에서 제외하는 것이 좋습니다.

\[주소록 → 필터 → 구독자 활동: 발송 실패, 오픈 안함] 경로를 통해 오랫동안 이메일을 열어보지 않았거나 발송에 실패한 구독자를 찾을 수 있습니다. 프로 요금제부터 사용할 수 있는 \[세그먼트]의 \[구독자 활동 기록] 기반 기능을 사용하면 일정 기간 이메일을 열어보지 않거나 발송에 실패하는 구독자를 자동으로 분류해 보다 손쉽게 관리할 수 있습니다.

{% content-ref url="../list/classify-subscribers/how-to-use-segment.md" %}
[how-to-use-segment.md](../list/classify-subscribers/how-to-use-segment.md)
{% endcontent-ref %}



#### 수신거부 링크 추가하기 <a href="#h_01hkxtbqn0vf0tfyfhfq8txg30" id="h_01hkxtbqn0vf0tfyfhfq8txg30"></a>

이메일에 수신자가 수신거부 의사를 표시할 수 있는 적절한 수단이 없다면 스팸으로 표시될 수 있습니다. 구독자가 수신에 동의했다고 해도 더 이상 이메일을 받아보고 싶지 않을 수 있을 때 수신을 거부할 방법이 없다면 ‘스팸 신고’를 할 가능성이 높습니다. 스팸 신고를 하게 되면 발신자 주소 평판에 영향이 발생하기 때문에 구독자가 이메일을 받아보고 싶지 않을 때 수신거부 방법을 마련해주는 것이 필요합니다.

에디터의 \[수신거부] 기능을 사용하면 이메일에 간단하게 수신거부 링크를 넣을 수 있습니다.

{% content-ref url="../email/edit/unsubscribe.md" %}
[unsubscribe.md](../email/edit/unsubscribe.md)
{% endcontent-ref %}



#### 이메일의 제목, 내용 수정하기 <a href="#h_01hkxtbqn094b5hwaw3163r0n4" id="h_01hkxtbqn094b5hwaw3163r0n4"></a>

이메일 수신 서비스는 이메일의 콘텐츠가 스팸성 이메일의 패턴을 따르는지 확인합니다. 자신들의 콘텐츠 정책에 따라 이메일의 내용이 스팸으로 판단한다면 이메일은 스팸으로 표시하여 별도로 관리하거나 수신을 차단합니다. 뒤이어 안내할 ‘기술적인 조치’ 에 따라 모든 조치를 했지만 계속해서 스팸 메일로 분류된다면 그때는 콘텐츠의 문제일 수 있으니, 제목이나 내용을 바꿔가며 테스트를 해보는 것이 좋습니다.&#x20;

구독자의 참여(오픈, 클릭)를 유도하기 위해 개인화된 콘텐츠를 만드는 것도 좋습니다. \[메일머지] 기능을 사용하면 이메일의 제목 또는 내용에서 구독자의 이름을 불러주거나 여러 가지 변수를 사용해 더 개인화된 느낌의 이메일을 보낼 수 있습니다.

수신 서비스는 눈에 보이는 단어, 문장뿐 아니라 이메일을 구성하는 눈에 보이지 않는 HTML 코드가 적절한지 여부도 검사합니다. 이메일 환경에서 호환되지 않는 HTML 코드가 섞여 있는 경우 스팸 메일로 판단하기도 합니다. 스티비 에디터를 사용한다면 이메일 환경에 최적화된 HTML 코드와 구조를 제공하기 때문에 이 문제를 해결할 수 있습니다.

{% hint style="info" %}
에디터를 사용한다고 해도 외부에서 작업한 텍스트를 그대로 복사해서 붙여 넣는 경우 눈에 보이지 않는 HTML 코드가 섞여 들어가 문제를 일으킬 수 있습니다. 외부에서 텍스트를 작업한 경우에는 ‘텍스트만 붙여넣기’를 사용해 텍스트 자체만 붙여 넣고 스타일은 스티비 에디터 내에서 편집하는 것을 권장합니다.
{% endhint %}



### 기술적인 조치 <a href="#h_01hkxtbqn0d3ajqn511p2dre3q" id="h_01hkxtbqn0d3ajqn511p2dre3q"></a>

기술적인 조치는 자신만의 개인화된 이메일 주소를 가지고 있는 경우에만 설정할 수 있습니다. 예를 들어 gmail.com, naver.com 등의 공개된 도메인을 가진 발신자 주소를 사용하는 경우에는 조치가 불가능합니다. 공개된 이메일 주소를 사용해 이메일을 보내는 경우 이메일의 전송 속도가 제한되거나 차단되거나 스팸으로 표시될 수 있습니다. 따라서 도메인을 구입해 나만의 발신자 주소를 만들어 사용하는 것을 권장합니다.

{% content-ref url="../getting-started/preparing-for-start/custom-sender-address.md" %}
[custom-sender-address.md](../getting-started/preparing-for-start/custom-sender-address.md)
{% endcontent-ref %}



#### 이메일이 발송되는 서버의 IP 평판 유지하기 <a href="#h_01hkxtbqn0zt0nq18qgbtmthyy" id="h_01hkxtbqn0zt0nq18qgbtmthyy"></a>

이메일 수신 서비스에서는 이메일이 발송된 서버의 평판을 참고합니다. 평판이 낮은 서버에서 발송된 경우 이 이메일을 스팸으로 분류할 확률이 높습니다. 스티비를 사용하는 경우 이메일 발송은 스티비의 발송 서버를 사용해 이루어집니다. 스티비 팀에서는 서비스를 사용해 발송되는 이메일을 모니터링하고 스팸 메일 정책에 따라 회원의 스팸 메일 발송을 관리하여 높은 평판 상태를 유지하기 위해 노력하고 있습니다.



#### SPF, DKIM 설정하기 <a href="#h_01hkxtbqn0casvd7cmfspnv1y0" id="h_01hkxtbqn0casvd7cmfspnv1y0"></a>

SPF(Sender Policy Framework)와 DKIM(Domainkeys Identified Mail)은 발신자의 신뢰도를 검증하기 위해 대부분의 수신 서비스에서 널리 사용하고 있는 방법입니다.\
\
스티비와 같은 이메일 마케팅 서비스를 사용해 이메일을 보내면 내가 가지고 있는 발송 서버가 아닌 사용하는 서비스에서 가지고 있는 서버로 발송이 이루어집니다. 따라서 내가 가지고 있는 서버가 아닌 다른 곳에서 내 발신자 주소를 사용해 이메일을 보내고 있다면 수신 서비스 쪽에서는 이 이메일을 의심스럽다고 판단할 수 있습니다.\
\
스티비의 SPF, DKIM을 설정하면 "스티비의 서버에서 발송된 이메일도 내가 보낸 것이 맞다."는 것을 수신 서비스에 안내해 발신자 주소의 신뢰도를 확보하고 스팸으로 분류되는 비율을 낮출 수 있습니다. 자세한 내용은 [SPF, DKIM 설정하기](prevent-email-spam-marking.md#h_01hkxtbqn0casvd7cmfspnv1y0) 도움말을 참고해 주세요.&#x20;



#### DMARC 설정 적용하기 <a href="#h_01hkxtbqn0wpdw6gzjp9nz0sdc" id="h_01hkxtbqn0wpdw6gzjp9nz0sdc"></a>

DMARC(Domain-based Message Authentication, Reporting & Conformance)는 누군가 이메일 주소를 도용하여 발송하는 것을 막기 위해 사용하는 설정입니다. DMARC 설정을 하면 누군가 내 발신자 이메일 주소와 똑같은 가짜 주소를 사용해 스팸 메일을 보내는 것을 방지할 수 있습니다. 발신자 주소를 사칭해 보내는 것이 불가능해지면 이메일이 스팸으로 표시되는 비율이 낮아지고 그 결과 발신자 주소의 평판도 좋아집니다. 평판이 좋은 발신자 주소에서 보내는 이메일은 일반적으로 스팸으로 표시될 확률이 낮습니다.\
\
DMARC 설정이 된 도메인에서 보내는 이메일은 사칭자가 보낸 이메일일 확률이 낮습니다. DMARC 설정이 된 도메인에서 보내는 이메일은 상대적으로 그렇지 않은 도메인보다 안전한 이메일일 확률이 높고 이메일 수신 서비스에서도 결과적으로는 DMARC 설정이 된 도메인에서 발송되는 이메일을 더 선호합니다. 자세한 설정 방법은 [DMARC 설정 적용하기](../email/managing-sender/dmarc.md) 도움말을 참고해 주세요.



#### 모니터링 하기 <a href="#h_01hkxtbqn0fswkpqgfbaa8w5ez" id="h_01hkxtbqn0fswkpqgfbaa8w5ez"></a>

개인화된 발신자 이메일 주소로 이메일을 보낸다면 내가 보낸 이메일이 얼마나 스팸으로 분류되고 있는지 비율을 확인할 수 있습니다. 구글에서 제공하는 포스트마스터 툴(Postmaster Tools)을 사용하면 비율을 확인할 수 있습니다. 자세한 설정 방법은 [스팸 분류 비율 확인하기](../email/send/spam-rate.md) 도움말을 참고해 주세요.

대표적인 이메일 수신 서비스 G메일에서는 스팸 메일로 분류되는 비율을 0.3% 미만으로 관리할 것을 권고하고 있습니다. 모니터링 결과 스팸함으로 분류되는 비율이 기준을 초과한다면 취하지 않은 기술적인 조치들이 있는지 확인해 보는 것이 좋습니다. 모든 조치를 진행했지만 비율이 여전히 기준을 초과한다면, 그때는 관리적인 조치를 수행하며 스팸 분류 비율을 관리하는 것이 좋습니다.
