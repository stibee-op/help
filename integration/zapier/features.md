# 주요 기능 살펴보기

💬 이 내용은 **스탠다드, 프로, 엔터프라이즈** 요금제에 해당하는 도움말입니다.

## 이 글에서는

Zapier 스티비 앱에서 지원하는 액션 이벤트를 알아보고, 사용할 수 있는 시나리오를 살펴봅니다.

***

## Action event 종류

현재 Zapier 스티비 앱에서 제공하는 Action event는 다음과 같습니다.

* Add Subscriber(구독자 추가)  : 주소록에 구독자를 추가합니다.
* Add Subscriber to Group(구독자 그룹 할당): 특정 그룹에 구독자를 분류합니다.
* Add Subscriber With Double-Opt-In(구독자 추가 - 구독 확인 이메일 발송): 구독 확인 이메일을 발송합니다. 구독 확인 이메일에서 인증을 완료해야 구독자로 추가됩니다.
* Create Empty Email(이메일 생성)  : 새로운 이메일을 생성합니다. 제목, 발송할 주소록(또는 그룹, 세그먼트), 발신자 이메일 주소, 발신자 이름을 설정할 수 있습니다.
* Delete Subscriber(구독자 완전 삭제)  : 주소록에서 구독자를 삭제합니다.
* Delete Subscriber From Group(구독자 그룹 해제): 특정 그룹에서 구독자를 삭제합니다. 주소록에서 구독자가 삭제되는 것은 아닙니다.
* Send Email(이메일 발송)  : 이메일을 발송합니다.&#x20;
* Unsubscribe(구독자 수신거부): 구독자를 수신거부 상태로 변경합니다.
* Update Email Content With HTML  (이메일 콘텐츠 수정): 이메일 콘텐츠를 HTML 코드를 사용해 수정합니다.
* Update Subscriber(구독자 정보 수정): 구독자 정보를 업데이트합니다.

_\* 지금은 스티비 앱에서 구독자 관리와 이메일 생성/발송과 관련된 주요 API만 사용하실 수 있습니다. 다른 API도 점차 추가할 예정입니다._



## 주요 시나리오

### 구글 폼(Google Forms), 타입폼(Typeform)과 연동하기

구글 폼, 타입폼에 도착한 새로운 응답을 스티비 주소록에 자동 등록할 수 있습니다. 설문조사, 피드백 등을 통해 수집한 구독자 정보를 스티비 주소록에 손쉽게 연동해 보세요.

자세한 내용은 아래 도움말을 참고해 주세요.

{% content-ref url="../../how-to-use-zapier/google-forms.md" %}
[google-forms.md](../../how-to-use-zapier/google-forms.md)
{% endcontent-ref %}

{% content-ref url="../../how-to-use-zapier/typeform.md" %}
[typeform.md](../../how-to-use-zapier/typeform.md)
{% endcontent-ref %}

### 구글 스프레드시트와 연동하기

구글 스프레드시트에 새로운 정보가 추가되면 스티비 주소록에 구독자로 자동 등록할 수 있습니다.&#x20;

자세한 내용은 아래 도움말을 참고해 주세요.

{% content-ref url="../../how-to-use-zapier/spreadsheets.md" %}
[spreadsheets.md](../../how-to-use-zapier/spreadsheets.md)
{% endcontent-ref %}
