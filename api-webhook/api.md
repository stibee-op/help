# API 사용하기

💬 이 내용은 **스탠다드, 프로, 엔터프라이즈 요금제**에 해당하는 도움말입니다.

## 이 글에서는 <a href="#h_01hrp9h7hbxw06bj9p21fev150" id="h_01hrp9h7hbxw06bj9p21fev150"></a>

API키 생성부터 사용할 수 있는 연동 종류까지 스티비에서 제공하는 API를 사용하기 위해 기본적으로 알아야 하는 내용에 대해 알아봅니다.

{% hint style="info" %}
API에 대한 요청 및 응답 방법은 [스티비 API 문서](https://developers.stibee.com/)에서 확인하고 테스트할 수 있습니다.
{% endhint %}

***

## API 종류 <a href="#api-types" id="api-types"></a>

스티비에서 제공하는 API는 크게 '이메일'과 '주소록' 두 가지로 나뉩니다.&#x20;

* 이메일 API: 이메일을 생성하거나 콘텐츠를 수정하고 발송할 수 있으며, 발송한 이메일의 통계를 조회할 수 있습니다.
* 주소록 API: 주소록을 생성하거나 정보를 수정할 수 있고 주소록에 구독자를 추가하거나 정보를 수정할 수 있습니다. 주소록에 구독자를 나눠서 관리할 수 있는 \[[그룹](../list/classify-subscribers/how-to-use-groups.md)]을 만들거나 수정할 수 있고 주소록에 발신자 이메일 주소를 추가하거나 삭제할 수 있습니다.

| API         | 스탠다드 | 프로 | 엔터프라이즈 |
| ----------- | ---- | -- | ------ |
| 구독자         | ✅    | ✅  | ✅      |
| 이메일, 그룹     | -    | ✅  | ✅      |
| 주소록, 발신자 주소 | -    | -  | ✅      |



## 시작하기 <a href="#getting-started" id="getting-started"></a>

### API 키 만들기 <a href="#api-key" id="api-key"></a>

API를 사용하기 위해서는 API 키를 만들어야 합니다. API는 워크스페이스 단위로 관리되므로 \[워크스페이스 이름 → 워크스페이스 설정 → API 키]에서 \[+새로 만들기]를 눌러 API 키를 생성할 수 있습니다.

<figure><img src="../.gitbook/assets/image (140).png" alt=""><figcaption></figcaption></figure>

\[+새로 만들기]를 클릭해서 API 키를 생성한 뒤, \[복사하기]를 누르면 API 키를 복사할 수 있습니다. 이 키는 API 요청 시 토큰으로 사용됩니다. API 키는 최대 10개까지 생성할 수 있습니다.

**\*주의:** API 키가 노출되면 워크스페이스 보안에 치명적인 문제가 생길 수 있습니다. API 키 노출이 의심된다면 의심되는 키를 비활성화하거나 삭제한 뒤, 새로운 키를 만들어서 사용해 주세요.

<figure><img src="../.gitbook/assets/image (141).png" alt=""><figcaption></figcaption></figure>



### API 요청에 필요한 키 값 확인하기 <a href="#find-ids" id="find-ids"></a>

API 요청을 보낼 때 어떤 이메일, 주소록, 그룹 등에 대한 요청인지 구체적으로 지정해야 합니다. 각 이메일, 주소록, 그룹은 고유의 ID 값을 가지고 있고 이 ID는 브라우저의 URL에서 확인할 수 있습니다.

#### emailId(이메일 ID) <a href="#email-id" id="email-id"></a>

emailId는 이메일에 할당된 고유의 아이디입니다. 아래 방법으로 확인할 수 있습니다.

1. 이메일 목록에서 ID를 확인하고 싶은 이메일의 이름을 클릭하여 편집 화면 또는 \[이메일 대시보드]로 이동
2. 브라우저에 표시되는 URL에서 'email' 뒤의 숫자를 확인(예: https://stibee.com/email/123456/... 일 때  emailid는 email 뒤에 있는 123456)

#### listId(주소록 ID) <a href="#list-id" id="list-id"></a>

listId는 주소록에 할당된 고유의 아이디입니다. 아래 방법으로 확인할 수 있습니다.

1. 주소록 목록에서 주소록 이름을 클릭하여 \[주소록 대시보드]로 이동
2. 브라우저에 표시되는 URL에서 'lists' 뒤의 숫자를 확인 (예: https://stibee.com/lists/123456/... 일 때 listid는 lists 뒤에 있는 123456)

#### groupId(그룹 ID) <a href="#group-id" id="group-id"></a>

groupId는 그룹에 할당된 고유의 아이디입니다. 아래 방법으로 확인할 수 있습니다.

1. 주소록 목록에서 주소록 이름을 클릭하여 \[주소록 대시보드]로 이동
2. \[그룹]을 클릭하여 그룹 목록으로 이동
3. 그룹 이름을 클릭하여 그룹 필터링이 적용된 구독자 목록으로 이동
4. 브라우저에 표시되는 URL에서 'S' 뒤의 숫자를 확인(예: https://stibee.com/lists/123456/subscribers/S/789012 일 때 groupId는 S 뒤에 있는 789012)

#### segmentId(세그먼트 ID) <a href="#segment-id" id="segment-id"></a>

segmentId는 세그먼트에 할당된 고유의 아이디입니다. 아래 방법으로 확인할 수 있습니다.

1. 주소록 목록에서 주소록 이름을 클릭하여 \[주소록 대시보드]로 이동
2. \[세그먼트]를 클릭하여 세그먼트 목록으로 이동
3. 세그먼트 이름을 클릭하여 세그먼트 필터링이 적용된 구독자 목록으로 이동
4. 브라우저에 표시되는 URL에서 'segment=' 뒤의 숫자를 확인(예: https://stibee.com/lists/123456/subscribers/S/all/0,1,2,3/1?segment=7890 일 때 segmentId는 'segment=' 뒤에 있는 7890)



### API 요청 속도 제한 <a href="#rate-limit" id="rate-limit"></a>

API 요청 속도 제한은 일정 시간 동안 스티비 API에 보낼 수 있는 요청 횟수의 상한입니다. 안정적인 서비스 제공을 위해 적용하며, 제한을 넘은 요청은 처리되지 않습니다. 요청 횟수는 워크스페이스 단위로 1분마다 계산합니다.

_\* 요금제별 권한과 정확한 요청 속도 제한은_ [_스티비 API 문서_](https://developers.stibee.com/)_의 API 항목 제목 위에도 표시됩니다._

<table><thead><tr><th>API</th><th width="190.43359375">요청 속도 제한</th><th>계산 방식</th></tr></thead><tbody><tr><td>구독자 대량 추가</td><td>최대 10회/분</td><td>따로 계산 </td></tr><tr><td>구독자 목록 조회</td><td>최대 100회/분</td><td>따로 계산</td></tr><tr><td>구독자 성과 조회</td><td>최대 100회/분</td><td>따로 계산</td></tr><tr><td>이메일 성과 조회</td><td>최대 100회/분</td><td>따로 계산</td></tr><tr><td>그 외 모든 API</td><td>최대 1000회/분</td><td>해당하는 API의 요청 횟수를 모두 합산</td></tr></tbody></table>

'그 외 모든 API'의 제한은 API마다 따로 적용되지 않습니다. 위 4개 API를 제외한 모든 API의 요청 횟수를 합산해 1분에 최대 1000회까지 처리합니다.

* 예. 이메일 상세 통계 조회 API를 1분에 1000회 요청하면, 같은 시간에 보낸 구독자 삭제 요청은 처리되지 않습니다.

{% hint style="info" %}
자동 이메일 API는 1초당 3회, 1회당 256KB로 제한합니다. 자동 이메일 API 사용과 관련한 자세한 내용은 [자동 이메일 API 사용하기](../email/automation/api.md) 도움말을 참고해 주세요.
{% endhint %}

#### **API 요청 속도 제한을 넘었을 때** <a href="#rate-limit-exceeded" id="rate-limit-exceeded"></a>

제한을 넘은 요청에는 HTTP 429와 함께 `Errors.Authorization.TooManyRequest`가 반환됩니다. 이때는 아래 내용을 확인해 주세요.

* 429 응답을 받은 API뿐 아니라 '그 외 모든 API'에 해당하는 다른 API의 요청 횟수도 함께 확인합니다.
* 요청 간격을 늘린 뒤 다시 시도합니다.



## API 연동하기 <a href="#integration" id="integration"></a>

API키를 만들고 이메일, 주소록, 그룹의 아이디를 확인하는 방법까지 알았다면 API 연동을 위한 기본적인 준비는 마무리 된 상황입니다. 지금부터는 스티비 API 문서를 참고해 원하는 기능을 구현하여 직접 사용하면 됩니다.

API 문서에서는 요청에 대한 응답을 테스트 해볼 수 있고 여러 언어별 구현 예제도 확인할 수 있습니다. API를 사용해 스티비의 더 확장된 기능을 경험해 보세요.

{% embed url="https://developers.stibee.com/" %}
