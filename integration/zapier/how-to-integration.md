# 연동하기

💬 이 내용은 **스탠다드, 프로, 엔터프라이즈** 요금제에 해당하는 도움말입니다.

## 이 글에서는

Zapier에서 스티비 앱을 사용하는 방법에 관해 알아봅니다.

***

## Zap 기본 구조 살펴보기

Zap은 'Trigger'와 'Action'으로 구성됩니다. Trigger에서 설정한 이벤트 조건을 충족하면, Action 이벤트가 실행되는 구조입니다.

예를 들어, 구글 스프레드시트에 새로운 이메일 주소가 추가되면 스티비 주소록에 구독자로 자동 등록되도록 설정하고 싶다면..

* Trigger: 구글 스프레드시트에 새로운 이메일 주소가 추가되는 이벤트를 설정합니다.
* Action: 스티비 주소록에 새로운 구독자로 등록되는 이벤트를 설정합니다.



## Zapier에서 스티비 앱 사용하기

아래 방법으로 Zapier에서 스티비 앱을 사용할 수 있습니다.



1. Zapier에 접속한 뒤, \[+Create -> Zaps]를 눌러 새로운 Zap을 생성합니다.

<figure><img src="../../.gitbook/assets/Zapier 스티비 앱 사용하기1.png" alt=""><figcaption></figcaption></figure>



2. Zap 설정 화면으로 이동합니다.

<figure><img src="../../.gitbook/assets/Zapier 스티비 앱 연동하기2 (1).png" alt=""><figcaption></figcaption></figure>



3. 'Trigger' 이벤트를 설정합니다.

**\* 주의:** 현재 Zapier 스티비 앱은 Action 이벤트만 지원합니다. 따라서, Trigger에서는 스티비 앱 사용이 불가합니다.

<figure><img src="../../.gitbook/assets/Zapier 스티비 앱 연동하기3.png" alt=""><figcaption></figcaption></figure>



4. Action에서 'Stibee'를 검색한 뒤, 원하는 'Action Event'를 설정합니다.   \
   &#xNAN;_\* 각 이벤트의 자세한 내용은_ [_주요 기능 살펴보기_](features.md) _도움말을 참고해 주세요._

<figure><img src="../../.gitbook/assets/Zapier 스티비 앱 연동하기4.png" alt=""><figcaption></figcaption></figure>

<div data-full-width="false"><figure><img src="../../.gitbook/assets/Zapier 스티비 앱 연동하기4-2.png" alt=""><figcaption></figcaption></figure></div>



5. Account에 API Key를 입력해 주세요.

API 키는 \[워크스페이스 이름 → 워크스페이스 설정 → API 키]에서 확인할 수 있습니다. 자세한 방법은 [API 사용하기](../../api-webhook/api.md#id-1-api-1) 도움말을 참고해 주세요.

**\*주의:** API 키가 노출되면 워크스페이스 보안에 치명적인 문제가 생길 수 있습니다. API 키 노출되지 않도록 유의해 주세요.

<figure><img src="../../.gitbook/assets/Zapier 스티비 앱 연동하기5.png" alt=""><figcaption></figcaption></figure>



6. 이후 필요한 조건 설정을 완료한 뒤, \[Publish]를 누르면 Zapier 스티비 앱 연동이 완료됩니다.

<figure><img src="../../.gitbook/assets/Zapier 스티비 앱 연동하기6.png" alt=""><figcaption></figcaption></figure>
