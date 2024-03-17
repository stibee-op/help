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

# 이메일 조회 API

💬 이 내용은 **스탠다드, 프로, 엔터프라이즈 요금제**에 해당하는 도움말입니다.

## 이 글에서는

이메일 조회 API의 개념과 API를 사용하는 기술적인 방법에 대해 설명하고 있습니다.



## 이메일 조회 API 이해하기

이메일 조회 API를 사용하면 '이메일 목록'과 각 이메일의 '[상세통계](../email/undefined-5/undefined-2.md)'를 불러올  수 있습니다. 이메일  조회 API를 사용하면 내가 만들고 발송한 이메일의 목록과 각 이메일의 통계를 외부에서 조회하고 활용할 수 있습니다.&#x20;

이메일 조회 API에서 사용할 수 있는 기능은 아래와 같습니다.

* 이메일 목록 조회: 워크스페이스에 생성된 이메일의 목록을 조회 할 수 있습니다.
* 이메일 상세 통계 조회: 발송한 이메일의 상세 통계를 조회 할 수 있습니다.



## 이메일 조회 API 사용하기

### API 키 만들기

&#x20;이메일 조회 API를 사용하려면 우선 스티비에서 API 키를 만들어야 합니다. API는 계정 단위로 관리되기 때문에 API 키의 생성과 관리는 모두 화면 오른쪽 위에 있는 \[워크스페이스 이름 → 워크스페이스 설 → API 키] 에서 이루어집니다.

<figure><img src="https://help.stibee.com/hc/article_attachments/7000529224079" alt=""><figcaption></figcaption></figure>

\[새로 만들기]를 클릭해 API 키를 생성한 뒤, API 키 옆의 \[복사하기]를 클릭하면 API 키를 복사할 수 있습니다. 이 키는 API 요청 시 토큰으로 사용됩니다. (API 키는 최대 10개까지 생성이 가능합니다.)&#x20;

<figure><img src="https://help.stibee.com/hc/article_attachments/7000529244175" alt=""><figcaption></figcaption></figure>

API 키가 노출되면 스티비 계정 보안에 치명적인 문제가 생길 수 있으니 주의하세요. 만약 노출이 의심되면 **계정** **API 키**에서 해당 키를 비활성화하거나 삭제하고 새로운 키를 만드세요.

### API 요청 및 응답 모델 <a href="#id-3-api" id="id-3-api"></a>

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
  "Value": [{
      "id": string,
      "status": string,
      "listId": string,
      "type": string,
      "subType": string,
      "subject": "string",
      "permanentLink": "string",
      "sentTime": "YYYY-MM-DDThh:mm:ss+09:00",
      "createdTime": "YYYY-MM-DDThh:mm:ss+09:00"
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
  * 2: AB테스트 이메일
  * 3: 자동 이메일
* **subtype**: type이 2일때 유효한 필드입니다.&#x20;
  * 1: 제목 기준 AB테스트
  * 2: 발신자 기준 AB테스트
  * 3: 스케쥴 기준 AB테스트
  * 4: 콘텐츠 기준 AB테스트
* **permanentLink**: 이메일의 공유용 URL 입니다.
* **sentTime**: 이메일을 발송한 일시입니다.&#x20;
* **createdTime:** 이메일을 만든 일시입니다.

이메일에 할당된 고유의 아이디(emailId)는 아래 방법으로 확인할 수 있습니다.

1. 이메일 목록에서 이메일 이름을 클릭하여 \[이메일 대시보드]로 이동
2. 브라우저에 표시되는 URL에서 email 뒤 dashboard 앞 숫자를 확인

주소록에 할당된 고유의 아이디(listId)는 아래 방법으로 확인할 수 있습니다.

1. 주소록 목록에서 주소록 이름을 클릭하여 \[주소록 대시보드]로 이동
2. 브라우저에 표시되는 URL에서 'lists' 뒤의 숫자를 확인

이메일 목록 조회 요청의 응답 예시는 [여기](api-1.md#undefined-2)를 참고해주세요.



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
  "Value": [{
      "id": string,
      "subscriber": "string",
      "action": "string",
      "value": "string",
      "createdTime": "YYYY-MM-DDThh:mm:dd+09:00"
    },
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
    * value: 브라우저 정보
  * C: 클릭
    * value: 클릭한 링크
    * value2: 브라우저 정보
  * D: 수신거부
* **createdTime**: 상세 통계가 기록된 날짜입니다.&#x20;

이메일 상세  통계조회 요청의 응답 예시는 [여기](api-1.md#undefined-2)를 참고해주세요.



## _AP_I 요청 및 응답 예제

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
  "Value": [{
      "id": 3442,
      "status": 3,
      "listId": 1547,
      "type": 1,
      "subType": 0,
      "subject": "이메일 A",
      "permanentLink": "http://stib.ee/aaa",
      "sentTime": "2022-01-25T12:22:36+09:00",
      "createdTime": "2022-01-25T12:22:36+09:00"
    },
    {
      "id": 3443,
      "status": 3,
      "listId": 1547,
      "type": 1,
      "subType": 0,
      "subject": "이메일 B",
      "permanentLink": "http://stib.ee/bbb",
      "sentTime": "2022-01-25T12:22:36+09:00",
      "createdTime": "2022-01-25T12:27:28+09:00"
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
  "Value": [{
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
