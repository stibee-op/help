# 구글 설문지로 새로운 구독자 연동하기

💬 이 내용은 **스탠다드, 프로, 엔터프라이즈** 요금제에 해당하는 도움말입니다.

## 언제 필요한가요?

* 구글 설문지(Google Forms)로 수집한 구독자 정보를 스티비 주소록에 자동으로 추가하고 싶을 때

***

{% hint style="info" %}
구글 설문지와 Zapier 스티비 앱을 연동하기 위해서는 구글 설문지가 생성된 상태여야 합니다. 또, 최소한 1개 이상의 응답이 미리 존재해야 정상적으로 Test Step을 진행할 수 있어요.
{% endhint %}

Zap은 'Trigger'와 'Action'으로 구성됩니다. Trigger에서 설정한 이벤트 조건을 충족하면, Action 이벤트가 실행되는 구조입니다.

_\* Zapier와 스티비를 연동하는 기본 방법은_ [how-to-integration.md](../integration/zapier/how-to-integration.md "mention") _도움말을 참고해 주세요._



### Trigger event 설정하기

1. Zapier에 접속한 뒤, \[+Create → Zaps]를 눌러 새로운 Zap을 생성합니다.
2. \[Trigger → Google Forms]을 선택합니다.
3. \[Trigger event → New Form Response]를 선택합니다.
4. 'Account'를 눌러 구글 설문지를 생성한 구글 계정으로 로그인한 뒤, 액세스 권한을 허용합니다.

<figure><img src="../.gitbook/assets/Zapier 구글 폼.png" alt=""><figcaption></figcaption></figure>

<figure><img src="../.gitbook/assets/Zapier 구글 폼2.png" alt=""><figcaption></figcaption></figure>



5. \[Continue]를 눌러 \[Configure] 단계로 이동한 뒤, 연동할 구글폼을 선택합니다.   \
   &#xNAN;_\* 구글 설문지와 Zapier 스티비 앱을 연동하기 위해서는 구글 설문지가 게시된 상태여야 합니다._
6. \[Test Trigger]를 눌러 설정이 잘 이루어졌는지 확인합니다.
7. \[Find new records]를 눌러 Test를 진행할 응답을 선택합니다.   \
   &#xNAN;_\* 연동한 구글 설문지에 최소 1개 이상의 응답이 존재해야 정상적으로 테스트가 진행됩니다._

<figure><img src="../.gitbook/assets/Zapier 구글 폼3 (1).png" alt=""><figcaption></figcaption></figure>



### Action event 설정하기

1. \[Action]을 클릭해 Stibee 앱을 검색한 뒤 선택합니다.
2. \[Action event → Add Subscriber]을 선택합니다.
3. 'Account'를 눌러 스티비 API key를 입력합니다.   \
   \* API key를 확인하는 자세한 방법은 [API 사용하기](../api-webhook/api.md#id-1-api-1) 도움말을 참고해 주세요.

<figure><img src="../.gitbook/assets/Zapier 구글 폼4 (1).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../.gitbook/assets/Zapier 스티비 앱 연동하기5.png" alt=""><figcaption></figcaption></figure>



4. \[Continue]를 눌러 \[Configure] 단계로 이동한 뒤, 스티비 주소록 정보를 입력합니다.

* List Id: 연동할 주소록 id를 입력합니다. 확인 방법은 [여기](https://help.stibee.com/api-webhook/api#listid-id)를 참고해 주세요.
* Email: 구독자 이메일 주소와 연동할 폼 응답입니다. \[+]를 눌러 응답을 선택해 주세요.
* Status: 구독 상태입니다. Subscribed는 구독 중 상태를 의미합니다.
* Custom Fields: 이메일 주소 외에 추가할 구독자 정보가 있다면 \[+]를 눌러 연동할 응답을 선택해 주세요.
* Marketing Allowed: 마케팅 정보 수신 동의 여부입니다.
* Update Enabled: 이미 존재하는 구독자일 경우, 이메일 주소 외에 나머지 정보를 업데이트할지 여부입니다. 기본값은 'Fasle(=업데이트하지 않음)' 입니다.

<figure><img src="../.gitbook/assets/Zapier 구글 폼5 (4).png" alt=""><figcaption></figcaption></figure>



5. \[Continue]를 눌러 \[Test] 단계로 이동한 뒤, \[Test step]을 누릅니다.   \
   &#xNAN;_\* 연동한 구글 설문지에 최소 1개 이상의 응답이 존재해야 정상적으로 테스트가 진행됩니다._
6. 문제가 없다면 \[Publish]를 눌러 Zap을 실행 상태로 만듭니다.

<figure><img src="../.gitbook/assets/Zapier 타입폼 5.png" alt=""><figcaption></figcaption></figure>



### 테스트 해보기

타입폼에 임의로 응답을 제출해 보세요. 스티비 주소록에 응답한 정보가 잘 연동됐다면 Zap 설정이 무사히 완료된 것입니다.
