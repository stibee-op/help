# 비공개 API

💬 이 내용은 **스탠다드, 프로, 엔터프라이즈 요금제**에 해당하는 도움말입니다.

## 이메일 조회 API

## 이 글에서는

이메일 조회 API의 개념과 API를 사용하는 기술적인 방법에 관해 알아봅니다.



## 이메일 조회 API 이해하기

이메일 조회 API를 사용하면 내가 만들고 발송한 이메일의 목록과 개별 이메일의 통계를 외부에서 조회하고 활용할 수 있습니다.

이메일 조회 API에서 사용할 수 있는 기능은 아래와 같습니다.

* 이메일 목록 조회: 워크스페이스에 생성된 이메일의 목록을 조회 할 수 있습니다.
* 이메일 상세 통계 조회: 발송한 이메일의 상세 통계를 조회 할 수 있습니다.



## 이메일 조회 API 사용하기

#### API 키 만들기

주소록 API를 사용하기 위해서는 스티비에서 API 키를 만들어야 합니다. API는 워크스페이스 단위로 관리되기 때문에 API 키의 생성과 관리는 모두 화면 오른쪽 위에 있는 \[워크스페이스 이름 → 워크스페이스 설정 → API 키] 에서 이루어집니다.

<figure><img src="https://help.stibee.com/hc/article_attachments/7000529224079" alt=""><figcaption></figcaption></figure>



\[새로 만들기]를 클릭해 API 키를 생성한 뒤 \[복사하기]를 클릭하면 API 키를 복사할 수 있습니다. 이 키는 API 요청 시 토큰으로 사용됩니다. API 키는 최대 10개까지 생성할 수 있습니다.

<figure><img src="https://help.stibee.com/hc/article_attachments/7000529244175" alt=""><figcaption></figcaption></figure>



**\*주의:** API 키가 노출되면 스티비 워크스페이스 보안에 치명적인 문제가 생길 수 있으니 주의하세요. 만약, 노출이 의심되면 해당 키를 비활성화하거나 삭제한 뒤 새로운 키를 만들어서 사용해 주세요.



## API 요청 및 응답 모델 <a href="#id-3-api" id="id-3-api"></a>

API 요청 및 응답은 JSON 형식을 따릅니다. 예를 들어, 워크스페이스의 이메일 목록을 조회하려면 GET Method로 JSON 형식의 요청을 보냅니다. API 요청에 대한 정책은 아래와 같이 운영하고 있습니다.

* API 요청은 1초당 10회로 제한됩니다.
* API 요청은 1회당 256KB로 제한됩니다.&#x20;



### 공통 <a href="#h_979f141299" id="h_979f141299"></a>

**Header**

* AccessToken: API 키
* Content-Type: application/json



### 이메일 목록 조회

* **HTTP Methods:** GET
* **Endpoint URL:** https://api.stibee.com/v1/emails



#### Request Body

이메일 목록 조회 요청의 응답은 아래 포맷을 가집니다.

```json
200 OK
Content-Type: application/json

{
  "Ok": true,
  "Error": null,
  "Value": [
    {
      "id": 0,
      "status": 0,
      "listId": 0,
      "type": 0,
      "subType": 0,
      "subject": "string",
      "permanentLink": "string",
      "permanentLinkSecondary": "string",
      "archiveContentType": 0,
      "sentTime": "YYYY-MM-DDThh:mm:ss+09:00",
      "createdTime": "YYYY-MM-DDThh:mm:ss+09:00",
      "tags": [
        {
          "id": 0,
          "name": "string"
        }
      ]
    }
  ]
}
```

* **Ok**: 요청에 대한 성공/실패 여부를 구분합니다. (true: 성공, false: 실패)
* **Error**: 요청 실패 원인이 표시됩니다. 에러 코드와 에러 메시지가 표시됩니다.
  * code: 에러 코드
  * message: 에러 메세지
* **id**: 이메일 별로 부여되는 고유한 아이디(id) 값 입니다.
* **status**: 이메일의 현재 상태를 의미합니다.
  * 0: 작성중
  * 1: 발송예약
  * 21: 처리 중
  * 22: 발송중
  * 3: 발송완료
  * 41: 발송 실패(일반 오류)
  * 42: 발송 실패(스팸)
* **listId**: 이메일을 발송한 주소록에 주소록 별로 부여되는 고유한 아이디(id) 값 입니다.
* **type**: 이메일의 종류를 의미합니다.
  * 1: 일반이메일
  * 2: [A/B테스트](../email/a-b-test.md) 이메일
  * 3: 자동 이메일
* **subtype**: type이 2일때 유효한 필드입니다.&#x20;
  * 1: 제목 기준 A/B테스트
  * 2: 발신자 기준 A/B테스트
  * 3: 스케쥴 기준 A/B테스트
  * 4: 콘텐츠 기준 A/B테스트
* **permanentLink**: 이메일의 공유용 URL 입니다.
* **permanentLinkSecondary**: type이 3이고 subType이 4인 경우에만 유효한 필드입니다. A/B 테스트 중인 B 이메일의 공유용 URL을 의미합니다.
* **archiveContentType**: type이 3이고 subType이 4인 경우에만 유효한 필드입니다. A/B테스트 한 이메일 중 '콘텐츠 발행 설정'을 한 콘텐츠가 A안인지 B안 인지 표시합니다.
* **sentTime**: 이메일을 발송한 일시입니다.&#x20;
* **createdTime:** 이메일을 만든 일시입니다.
* **tags**: 이메일에 설정한 [태그](../email/manage/tag.md) 정보를 의미합니다.
  * &#x20;id: 태그에 부여되는 고유한 ID 값 입니다.
  * name: 설정한 태그 이름입니다.

이메일에 할당된 고유의 아이디(emailId)는 아래 방법으로 확인할 수 있습니다.

1. 이메일 목록에서 이메일 이름을 클릭하여 \[이메일 대시보드]로 이동
2. 브라우저에 표시되는 URL에서 email 뒤 dashboard 앞 숫자를 확인

주소록에 할당된 고유의 아이디(listId)는 아래 방법으로 확인할 수 있습니다.

1. 주소록 목록에서 주소록 이름을 클릭하여 \[주소록 대시보드]로 이동
2. 브라우저에 표시되는 URL에서 'lists' 뒤의 숫자를 확인

이메일 목록 조회 요청의 응답 예시는 [여기](api.md#undefined-2)를 참고해주세요.



### 이메일 상세 통계 조회

* **HTTP Methods:** GET
* **Endpoint URL:** https://api.stibee.com/v1/emails/{emailId}/logs?offset=0\&startDate={startDate}\&endDate={endDate}

{emailId}에 입력한 이메일의 고유한 아이디 값을 기준으로 어떤 이메일의 상세통계를 조회할지 결정합니다. {startDate}와 {endDate}에 입력한 값을 기준으로 상세 통계를 조회할 기간을 설정합니다.

* **emailId**: 이메일 별로 부여되는 고유한 아이디(id) 값 입니다.
* **startDate**: 상세통계 조회 기간 중 '시작일'을 입력합니다.(YYYYMMDD)
* **endDate**: 상세통계 조회 기간 중 '마지막 날'을 입력합니다.(YYYYMMDD)

이메일에 할당된 고유의 아이디(emailId)는 아래 방법으로 확인할 수 있습니다.

1. 이메일 목록에서 이메일 이름을 클릭하여 \[이메일 대시보드]로 이동
2. 브라우저에 표시되는 URL에서 email 뒤 dashboard 앞 숫자를 확인

#### Request Body

이메일 상세 통계조회 요청의 응답은 아래 포맷을 가집니다.

```json
200 OK
Content-Type: application/json

{
  "Ok": true,
  "Error": null,
  "Value": [
    {
      "id": 0,
      "subscriber": "string",
      "action": "string",
      "value": "string",
      "createdTime": "YYYY-MM-DDThh:mm:dd+09:00"
    }
  ]
}
```

* **Ok**: 요청에 대한 성공/실패 여부를 구분합니다. (true: 성공, false: 실패)
* **Error**: 요청 실패 원인이 표시됩니다. 에러 코드와 에러 메시지가 표시됩니다.
  * code: 에러 코드
  * message: 에러 메세지
* **id**: 각 상세통계 별로 부여된 고유한 아이디 값입니다.
* **subscriber**: 상세통계가 기록된 구독자 이메일 주소입니다.
* **action**: 상세통계입니다.
  * P: 발송성공
  * F: 발송실패(소프트바운스)
    * value: 실패 이유
  * A: 발송실패(하드바운스)
    * value: 실패 이유
  * B: 발송실패(하드바운스)
    * value: 실패 이유
  * O: 오픈
    * value: 클릭이 발생한 클라이언트의 User-Agent 헤더 정보
  * C: 클릭
    * value: 클릭한 링크
    * value2: 클릭이 발생한 클라이언트의 User-Agent 헤더 정보
  * D: 수신거부
* **createdTime**: 상세 통계가 기록된 날짜입니다.&#x20;

이메일 상세  통계조회 요청의 응답 예시는 [여기](api.md#undefined-2)를 참고해주세요.



## _A_PI 요청 및 응답 예제

### 이메일 목록 조회 요청 및 응답  예제

2개의 이메일이 생성된 워크스페이스의 이메일 목록을 조회했을 때의 요청 및 응답 예제는 아래와 같습니다.

```json
GET https://api.stibee.com/v1/emails

AccessToken: API key

200 OK
Content-Type: application/json

{
  "Ok": true,
  "Error": null,
  "Value": [
    {
      "id": 1962151,
      "status": 3,
      "listId": 284039,
      "type": 3,
      "subType": 4,
      "subject": "스티비 이메일 에디터를 체험해보세요",
      "permanentLink": "https://stib.ee/A0dA",
      "permanentLinkSecondary": "https://stib.ee/B0dA",
      "archiveContentType": "",
      "sentTime": "2024-01-12T10:47:59+09:00",
      "createdTime": "2024-01-12T10:47:00+09:00",
      "tags": null
    },
    {
      "id": 1963356,
      "status": 3,
      "listId": 284039,
      "type": 1,
      "subType": 0,
      "subject": "fnsthnsgnsnsrgnsrnsr",
      "permanentLink": "https://stib.ee/BddA",
      "permanentLinkSecondary": "https://stib.ee/CddA",
      "archiveContentType": "",
      "sentTime": "2024-01-12T18:11:38+09:00",
      "createdTime": "2024-01-12T18:11:31+09:00",
      "tags": null
    },
    {
      "id": 1966392,
      "status": 3,
      "listId": 301309,
      "type": 1,
      "subType": 0,
      "subject": "aha",
      "permanentLink": "https://stib.ee/5EfA",
      "permanentLinkSecondary": "https://stib.ee/6EfA",
      "archiveContentType": "",
      "sentTime": "2024-01-15T17:34:15+09:00",
      "createdTime": "2024-01-15T17:33:23+09:00",
      "tags": [
        {
          "id": 17389,
          "name": "sadfsadf"
        }
      ]
    }
  ]
}
```



### 이메일 상세 통계 조회 요청 및 응답 예제

고유한 아이디 값이 1234인 이메일의 2024년 3월 1일 \~ 2024년 3월 10일까지 기록된 상세 통계를 조회했을 때의 요청 및 응답 예제는 아래와 같습니다.

<pre class="language-json"><code class="lang-json">GET https://api.stibee.com/v1/emails/1234/logs?offset=0&#x26;startDate=20240301&#x26;endDate=20240310

AccessToken: API key

<strong>200 OK
</strong>Content-Type: application/json

{
  "Ok": true,
  "Error": null,
  "Value": [
    {
      "id": 1,
      "subscriber": "dooly@stibee.com",
      "action": "P",
      "value": "해당없음",
      "createdTime": "2022-01-25T12:26:09+09:00"
    },
    {
      "id": 2,
      "subscriber": "gildong@stibee.com",
      "action": "O",
      "value": "Mozilla/5.0 (Windows NT 10.0; WOW64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/55.0.2883.87 Safari/537.36",
      "createdTime": "2022-01-25T12:26:36+09:00"
    },
    {
      "id": 3,
      "subscriber": "gildong@stibee.com",
      "action": "C",
      "value": "https://stibee.com",
      "value2": "Mozilla/5.0 (Windows NT 10.0; WOW64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/55.0.2883.87 Safari/537.36",
      "createdTime": "2022-01-25T12:26:36+09:00"
    }
  ]
}
</code></pre>



### 주소록 조회

* **HTTP methods**: GET
* **Endpoint URL**: https://api.stibee.com/v1/lists?offset=0\&limit=10\&sortBy={sortBy}\&orderBy={orderBy}

{sortBy}와 {orderBy}에 입력한 값을 기준으로 조회한 결과 값을 어떤 기준과 순서로 정렬할지 결정합니다.&#x20;

* **sortBy:** 조회한 결과의 정렬 기준을 입력합니다.&#x20;
  * **createdTime**: 주소록의 생성일 기준으로 조회 목록을 정렬합니다.
  * **Id**: 주소록에 할당한 고유한 ID값을 기준으로 조회 목록을 정렬합니다.
  * **name:** 주소록의 이름을 기준으로 조회 목록을 정렬합니다.
* **orderBy:** 조회한 결과의 정렬 순서를 입력합니다.&#x20;
  * **desc:** sortBy에서 설정한 기준에 따라 결과를 내림차순으로 정렬합니다.
  * **asc**: sortBy에서 설정한 기준에 따라 결과를 오름차순으로 정렬합니다.

#### Request Body

주소록 조회 요청의 응답은 다음 포맷을 가집니다.

#### 조회할 주소록이 없는 경우

```json
200 OK

{
  "Ok": true,
  "Error": null,
  "Value": null
}
```

#### **주소록 목록을 불러온 경우**

```json
200 OK
{
  "Ok": true,
  "Error": null,
  "Value": [
    {
      "id": 0,
      "name": "string",
      "createdTime": "YYYY-MM-DDThh:mm:ss+09:00"
    }
  ]
}
```

* **Ok**: 요청에 대한 성공/실패 여부를 구분합니다. (true: 성공, false: 실패)
* **Error**: 요청 실패 원인이 표시됩니다. 에러 코드와 에러 메시지가 표시됩니다.
  * Code: 에러 코드
  * Message: 에러 메시지
* **Value**: 요청 성공 결과가 표시됩니다. 결과 유형별로 Key-Value 배열 형식으로 표시됩니다.
  * id: 주소록에 할당한 고유한 아이디(ID) 값입니다.
  * name: 주소록의 이름입니다.
  * createdTime: 주소록이 만들어진 일시입니다.

주소록에 할당된 고유의 아이디는 아래 방법으로 확인할 수 있습니다.

1. 주소록 목록에서 주소록 이름을 클릭하여 \[주소록 대시보드]로 이동
2. 브라우저에 표시되는 URL에서 'lists' 뒤의 숫자를 확인

주소록 목록 조회 요청의 응답 예제는 [여기](api.md#undefined-6)에서 확인할 수 있습니다.



### 그룹 조회

* **HTTP methods**: GET
* **Endpoint URL**: https://api.stibee.com/v1/lists?/lists/{listId}/groups?offset=0\&limit=10\&sortBy={sortBy}\&orderBy={orderBy}

{listId}에는 그룹 목록을 조회하고 싶은 주소록의 고유한 ID 값을 입력합니다. {sortBy}와 {orderBy}에 입력한 값을 기준으로 조회한 결과 값을 어떤 기준과 순서로 정렬할지 결정합니다.

* **listId**: 주소록의 고유한 아이디 값을 입력합니다.
* **sortBy:** 조회한 결과의 정렬 기준을 입력합니다.&#x20;
  * **createdTime**: 주소록의 생성일 기준으로 조회 목록을 정렬합니다.
  * **Id**: 주소록에 할당한 고유한 ID값을 기준으로 조회 목록을 정렬합니다.
  * **name:** 주소록의 이름을 기준으로 조회 목록을 정렬합니다.
* **orderBy:** 조회한 결과의 정렬 순를 입력합니다.&#x20;
  * **desc:** sortBy에서 설정한 기준에 따라 결과를 내림차순으로 정렬합니다.
  * **asc**: sortBy에서 설정한 기준에 따라 결과를 오름차순으로 정렬합니다.

주소록에 할당된 고유의 아이디는 아래 방법으로 확인할 수 있습니다.

1. 주소록 목록에서 주소록 이름을 클릭하여 \[주소록 대시보드]로 이동
2. 브라우저에 표시되는 URL에서 'lists' 뒤의 숫자를 확인

#### Request Body

그룹 조회 요청의 응답은 다음 포맷을 가집니다.

#### 조회할  그룹이 없는 경우

```json
200 OK

{
  "Ok": true,
  "Error": null,
  "Value": null
}

```

#### 그룹 목록을 불러온 경우

```json
200 OK
{
  "Ok": true,
  "Error": null,
  "Value": [
    {
      "id": 0,
      "name": "string",
      "createdTime": "YYYY-MM-DDThh:mm:ss+09:00"
    },
    {
      "id": 0,
      "name": "string",
      "createdTime": "YYYY-MM-DDThh:mm:ss+09:00"
    }
  ]
}
```

* **Ok**: 요청에 대한 성공/실패 여부를 구분합니다. (true: 성공, false: 실패)
* **Error**: 요청 실패 원인이 표시됩니다. 에러 코드와 에러 메시지가 표시됩니다.
  * Code: 에러 코드
  * Message: 에러 메시지
* **Value**: 요청 성공 결과가 표시됩니다. 결과 유형별로 Key-Value 배열 형식으로 표시됩니다.
  * id: 주소록의  그룹에 할당한 고유한 아이디(ID) 값입니다.
  * name: 그룹의 이름입니다.
  * createdTime: 그룹이 만들어진 일시입니다.

그룹에 할당된 고유의 아이디는 아래 방법으로 확인할 수 있습니다.

1. 주소록 목록에서 주소록 이름을 클릭하여 \[주소록 대시보드]로 이동
2. \[그룹]을 클릭하여 그룹 목록으로 이동
3. 그룹 이름을 클릭하여 그룹 필터링이 적용된 구독자 목록으로 이동
4. 브라우저에 표시되는 URL에서 'subscribed' 뒤의 숫자를 확인

그룹 조회 요청의 응답 예제는 [여기](api.md#undefined-7)에서 확인할 수 있습니다.



### 구독자 숫자 조회

* **HTTP methods**: GET
* **Endpoint URL**: https://api.stibee.com/v1/lists/{listId}/subscribers/count?status={status}\&startDate={startDate}\&endDate={endDate}

{listId}에는 구독자 숫자를 조회하고 싶은 주소록의 고유한 ID 값을 입력합니다. {status}에는 숫자를 조회하고 싶은 구독자의 구독 상태를 입력합니다. {sortBy}와 {orderBy}에 입력한 값을 기준으로 조회한 결과 값을 어떤 기준과 순서로 정렬할지 결정합니다.

* **listId**: 주소록의 고유한 아이디 값을 입력합니다.
* **status**: 숫자를 조회하고 싶은 구독자의 구독 상태를 입력합니다. 입력하지 않으면 전체 숫자를 조회합니다.
  * S: 구독 상태가 '구독 중'인 구독자의 숫자를 조회합니다.
  * D: 구독 상태가 '수신거부'인 구독자의 숫자를 조회합니다.
  * A: 구독 상태가 '자동삭제'인 구독자의 숫자를 조회합니다.
* **startDate**: 조회하고 싶은 날짜의 시작일을 입력합니다. (YYYYMMDD)&#x20;
* **endDate**: 조회하고 싶은 날짜의 종료일을 입력합니다. (YYYYMMDD)

startDate와 endDate의 기준은  '구독자가 특정 구독 상태로 변경된 날짜'를 의미합니다. 예를 들어 dooly@stibee.com이라는 구독자가 2024년 3월 15일에 구독을 신청했다면 이 구독자가 '구독 중' 상태로 변경된 날은 2024년 3월  15일입니다. gildong.go@stibee.com 구독자가 2024년 3월 15일에 구독을 신청했고 '수신거부' 상태로 2024년 3월 16일에 변경됐다면 이 구독자가 '수신거부' 상태로 변경된 날은 2024년 3월 16일입니다.&#x20;



주소록에 할당된 고유의 아이디는 아래 방법으로 확인할 수 있습니다.

1. 주소록 목록에서 주소록 이름을 클릭하여 \[주소록 대시보드]로 이동
2. 브라우저에 표시되는 URL에서 'lists' 뒤의 숫자를 확인

#### Request Body

구독자 숫자 조회의 응답은 성공, 실패 여부에 따라 다음 포맷을 가집니다.



**응답 성공**

```json
200 OK
Content-Type: application/json

{
  "Ok": true,
  "Value": 0
}
```

* **Ok**: 요청에 대한 성공/실패 유무를 의미합니다. (true: 성공)
* **Value**: 조회한 구독자 숫자 결과가 표시됩니다.



**응답 실패**

```json
400 Bad Request
Content-Type: application/json

{
  "Ok": false,
  "Error": {
    "Code": "ERR-XXXX",
    "HttpStatusCode": 400,
    "Message": "Error Message"
  }
}
```

* **Ok**: 요청에 대한 성공/실패 유무를 의미합니다. (false: 실패)
* **Error**: 요청 실패 원인이 표시됩니다. 에러 코드와 에러 메시지가 표시됩니다.
  * Code: 에러 코드
  * HttpStatusCode: Http 에러 코드
  * Message: 에러 메시지

구독자 숫자 조회의 요청 및 응답 예제는 [여기](api.md#undefined-7)를 참고하세요.



### 구독자 목록 조회

* **HTTP methods**: GET
* **Endpoint URL**: https://api.stibee.com/v1/lists/{listId}/subscribers?status={status}\&startDate={startDate}\&endDate={endDate}\&offset={offset}\&limit={limit}

{listId}에는 구독자 목록을 조회하고 싶은 주소록의 고유한 ID 값을 입력합니다. {status}에는 목록을 조회하고 싶은 구독자의 구독 상태를 입력합니다. {sortBy}와 {orderBy}에 입력한 값을 기준으로 조회한 결과 값을 어떤 기준과 순서로 정렬할지 결정합니다. {offset}과 {limit}에는 전체 구독자 목록 중 몇번 째 값부터(offset) 구독자 목록을 조회할 지 그리고 한 페이지에 최대 몇개의 데이터를 표시할지 여부를 결정합니다.

* **listId**: 주소록의 고유한 아이디 값을 입력합니다.
* **status**: 목록을 조회할 구독 상태를 입력합니다. 입력하지 않으면 전체 구독를 조회합니다.
  * S: 구독 상태가 '구독 중'인 구독자 목록을 조회합니다.
  * D: 구독 상태가 '수신거부'인 구독자 목록을 조회합니다.
  * A: 구독 상태가 '자동삭제'인 구독자의 목록을 조회합니다.
* **startDate**: 조회하고 싶은 날짜의 시작일을 입력합니다. (YYYYMMDD)&#x20;
* **endDate**: 조회하고 싶은 날짜의 종료일을 입력합니다. (YYYYMMDD)
* **offset**: 페이징 처리를 위해 몇 번째 구독자부터 목록 조회를 시작할 지 여부를 결정합니다.
* **limit**: 페이징 처리를 위한 최대 기준을 설정합니다. (최대 1,000)

startDate와 endDate의 기준은  '구독자가 특정 구독 상태로 변경된 날짜'를 의미합니다. 예를 들어 dooly@stibee.com이라는 구독자가 2024년 3월 15일에 구독을 신청했다면 이 구독자가 '구독 중' 상태로 변경된 날은 2024년 3월  15일입니다. gildong.go@stibee.com 구독자가 2024년 3월 15일에 구독을 신청했고 '수신거부' 상태로 2024년 3월 16일에 변경됐다면 이 구독자가 '수신거부' 상태로 변경된 날은 2024년 3월 16일입니다.&#x20;

offset과 limit를 설정해 한번에 조회할 구독자의 목록을 설정할 수 있습니다. 예를 들어 1,000개의 데이터가 있다고 했을 때 offset을 0, limit를 100으로 설정하면 처음부터 100번째 까지의 구독자 목록을 조회합니다. offset을 100, limit를 100으로 설정하면 101번째부터 200번까지의 구독자 목록을 조회합니다.

####

#### Request Body

구독자 목 조회의 응답은 성공, 실패 여부에 따라 다음 포맷을 가집니다.



**응답 성공**

```json
200 OK
Content-Type: application/json
{
  "Ok": true,
  "Value": [
    {
      "created_time": "YYYY-MM-DD hh:mm:dd +0900 KST",
      "email": "string",
      "modified_time": "YYYY-MM-DD hh:mm:dd +0900 KST",
      "status": "string",
      "stb_ad_agreement": false
    }
  ]
}
```

* **Ok**: 요청에 대한 성공/실패 유무를 의미합니다. (true: 성공)
* **Value**: 조회한 구독자 숫자 결과가 표시됩니다.
  * created\_time: 주소록에 추가된 날짜
  * modified\_time: 구독자 정보가 변경된 날짜
  * status: 구독 상태
    * S: 구독 중
    * D: 수신거부
    * A: 자동삭제
* **stb\_ad\_agreement**: 구독자의 광고성 정보 수신 동의 여부를 의미합니다. (true: 동의함, false: 동의 안 함)

**응답 실패**

```json
400 Bad Request
Content-Type: application/json

{
  "Ok": false,
  "Error": {
    "Code": "ERR-XXXX",
    "HttpStatusCode": 400,
    "Message": "Error Message"
  }
}

```

* **Ok**: 요청에 대한 성공/실패 유무를 의미합니다. (false: 실패)
* **Error**: 요청 실패 원인이 표시됩니다. 에러 코드와 에러 메시지가 표시됩니다.
  * Code: 에러 코드
  * HttpStatusCode: Http 에러 코드
  * Message: 에러 메시지

구독자 목록 조회의 요청 및 응답 예제는 [여기](api.md#undefined-9)를 참고하세요.



### 주소록 목록 조회 응답 예제

주소록 목록 조회 요청의 응답 예시는 아래와 같습니다.

```json
200 OK
Content-Type: application/json

{
  "Ok": true,
  "Error": null,
  "Value": [
    {
      "id": 1235,
      "name": "주소록 B",
      "createdTime": "2020-03-03T23:44:57+09:00"
    },
    {
      "id": 1234,
      "name": "주소록 A",
      "createdTime": "2020-03-02T23:44:57+09:00"
    }
  ]
}
```



### 그룹 목록 조회 응답 예제

그룹 목록 조회 요청의 응답 예시는 아래와 같습니다.

```json
200 OK
Content-Type: application/json

{
  "Ok": true,
  "Error": null,
  "Value": [
    {
      "id": 1,
      "name": "그룹 A",
      "createdTime": "2020-03-02T23:44:57+09:00"
    },
    {
      "id": 2,
      "name": "그룹 B",
      "createdTime": "2020-03-03T23:44:57+09:00"
    }
  ]
}
```



### 구독자 숫자 조회 요청 및 응답 예제

주소록의 고유한 ID 값이 1234인 주소록에 2024년 3월 한달 동안 구독 중 상태로 추가된 구독자 숫자를 조회하기 위해 아래와 같이 조회했을 때 요청 값과 응답  성공 예제는 아래와 같습니다.

```json
GET https://api.stibee.com/v1/lists/1234/subscribers/count?status=S&startDate=20240301&endDate=20240331

AccessToken: API Key

200 OK
Content-Type: application/json

{
  "Ok": true,
  "Value": 30
}
```



### 구독자 목록 조회 요청 및 응답 예제

전체  구독자가  1,000명이 등록된 고유한 ID 값이 1234인 주소록에 2024년 3월 1일부터 2일까지 새로 추가된 구독자 목록을 조회하고 싶은 경우의 요청 값과 응답 성공 예제는 아래와 같습니다.

```json
GET https://api.stibee.com/v1/lists/1234/subscribers?status=S&startDate=20240301&endDate=20240302&offset=0&limit=2

AccessToken: API Key

200 OK
Content-Type: application/json

{
  "Ok": true,
  "Value": [
    {
      "createdTime": "2024-03-01 16:58:52 +0900 KST",
      "email": "gildong.go@stibee.com",
      "modifiedTime": "2024-03-01 16:58:52 +0900 KST",
      "status": "S"
    },
    {
      "createdTime": "2024-03-01 20:58:52 +0900 KST",
      "email": "dooly@stibee.com",
      "modifiedTime": "2024-03-01 20:58:52 +0900 KST",
      "status": "S"
    }
  ]
}
```