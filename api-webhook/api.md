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

# 주소록 API

💬이 내용은 **스탠다드, 프로, 엔터프라이즈 요금제**에 해당하는 도움말입니다.

## 이 글에서는 <a href="#h_01hrp9h7hbxw06bj9p21fev150" id="h_01hrp9h7hbxw06bj9p21fev150"></a>

주소록 API를 사용해 스티비 주소록과 가지고 있는 DB를 연동하는 방법에 대한 기술적인 방법을 알아봅니다.&#x20;

## 들어가기 전에 <a href="#h_01h9t7rjkw4a3mg81jvvh8g56g" id="h_01h9t7rjkw4a3mg81jvvh8g56g"></a>

주소록 API에 대한 요청 및 응답 방법은 [스티비 API 문서](https://api.stibee.com/docs)에서 확인하고 테스트해볼 수 있습니다.



## 주소록 API 이해하기 <a href="#h_01hrp917a0eyb3pcjd1crr02jk" id="h_01hrp917a0eyb3pcjd1crr02jk"></a>

주소록 API를 사용하면 스티비의 주소록과 내 서비스의 회원 정보를 연동하여 사용할 수 있습니다. 주소록 API를 사용하면 내 서비스에 회원이 새롭게 가입할 때마다 연동된 스티비 주소록에 자동으로 추가하거나 회원의 정보가 변경됐을 때 자동으로 주소록도 업데이트 하는 등 확장된 기능을 경험할 수 있습니다. 주소록 API는 [주소록 웹훅](https://help.stibee.com/hc/ko/articles/4756496712079)과 함께 사용해 내 DB와 주소록을 완전히 동기화하여 사용할 수 있습니다.

&#x20;

## 주소록 API 사용하기

### API 키 만들기 <a href="#id-1-api" id="id-1-api"></a>

주소록 API를 사용하려면 우선 스티비에서 API 키를 만들어야 합니다. API는 계정 단위로 관리되기 때문에 API 키의 생성과 관리는 모두 화면 오른쪽 위에 있는 \[워크스페이스 이름 → 워크스페이스 설 → API 키] 에서 이루어집니다.

<figure><img src="https://help.stibee.com/hc/article_attachments/7000529224079" alt=""><figcaption></figcaption></figure>

### &#x20; <a href="#id-2-api" id="id-2-api"></a>

\[새로 만들기]를 클릭해 API 키를 생성한 뒤, API 키 옆의 \[복사하기]를 클릭하면 API 키를 복사할 수 있습니다. 이 키는 API 요청 시 토큰으로 사용됩니다. (API 키는 최대 10개까지 생성이 가능합니다.)&#x20;

<figure><img src="https://help.stibee.com/hc/article_attachments/7000529244175" alt=""><figcaption></figcaption></figure>

API 키가 노출되면 스티비 계정 보안에 치명적인 문제가 생길 수 있으니 주의하세요. 만약 노출이 의심되면 **계정** **API 키**에서 해당 키를 비활성화하거나 삭제하고 새로운 키를 만드세요.\
\
API로 제공되는 기능은 다음과 같습니다.

* 구독: 주소록에 구독자를 추가합니다.
* 수신거부: 구독자를 수신거부 상태로 변경합니다.
* 완전삭제: 구독자를 완전삭제합니다. 구독자 정보와 활동 기록이 모두 삭제됩니다. 삭제된 구독자 정보와 활동 기록은 복구할 수 없습니다.
* 그룹 할당: 구독자를 주소록의 특정 그룹에 추가합니다.
* 그룹 해제: 구독자를 주소록의 특정 그룹에서 삭제합니다.
* 주소록 조회: 워크스페이스에 생성된 주소록 목록을 조회합니다. **(2024년 3월 15일 추가)**
* 그룹 조회: 주소록에 생성된 그룹 목록을 조회합니다. **(2024년 3월 15일 추가)**
* 구독자 숫자 조회: 주소록의 구독 상태별 구독자 수를 조회합니다. **(2024년 3월 15일 추가)**
* 구독자 목록조회: 주소록의 구독자 목록을 조회합니다. **(2024년 3월 15일 추가)**

(API로 제공되는 기능은 계속 추가될 예정입니다.)\


## API 요청 및 응답 모델 <a href="#id-3-api" id="id-3-api"></a>

API에 대한 요청 및 응답 방법은 [스티비 API 문서](https://api.stibee.com/docs)에서 확인하고 테스트해볼 수 있습니다.\
\
API 요청 및 응답은 JSON 형식을 따릅니다. 예를 들어, 주소록에 구독자를 추가하려면 POST Method로 다음과 같은 JSON 형식의 요청을 보냅니다. API 요청에 대한 정책은 아래와 같이 운영하고 있습니다.

* API 요청은 1초당 10회로 제한됩니다.
* API 요청은 1회당 256KB로 제한됩니다. 구독자 추가 시 약 2,000명을 한 번에 추가할 수 있는 사이즈입니다. 사용자 정의 필드 값에 따라 달라질 수 있습니다.

### 공통 <a href="#h_979f141299" id="h_979f141299"></a>

**Header**

* AccessToken: API 키
* Content-Type: application/json

### 구독 <a href="#h_5c2983c86c" id="h_5c2983c86c"></a>

* **HTTP Methods:** POST
* **Endpoint URL:** [https://api.stibee.com/v1/lists/{listid}/subscribers](https://api.stibee.com/v1/lists/%7Blistid%7D/subscribers)

listId(주소록에 할당된 고유의 아이디)는 아래 방법으로 확인할 수 있습니다.

1. 주소록 목록에서 주소록 이름을 클릭하여 \[주소록 대시보드]로 이동
2. 브라우저에 표시되는 URL에서 'lists' 뒤의 숫자를 확인

<figure><img src="https://help.stibee.com/hc/article_attachments/7000529244559" alt=""><figcaption></figcaption></figure>

#### **Request Body**

* **eventOccuredBy**: 구독자를 추가한 방법을 구분합니다.\
  \- "MANUAL": 관리자에 의해 추가한 것으로 기록합니다. (기본값)\
  \- "SUBSCRIBER": 구독자가 직접 구독한 것으로 기록합니다.
* **confirmEmailYN**: 구독 확인 이메일 발송 여부를 구분합니다.\
  \- "Y": 구독자에게 구독 확인 이메일을 발송하고, 구독자가 이 메일을 통해 구독 확인을 해야 구독자로 추가됩니다. 이 때 한 번에 추가하는 구독자가 10명을 초과하면 추가되지 않습니다.\
  \- "N": 구독 확인 과정없이 바로 구독자로 추가됩니다. (기본값)
* **groupIds**: 그룹에 할당된 고유의 아이디(groupId)입니다. 해당 그룹에 구독자를 할당하여 추가합니다. (기본값: 할당 안 함.)
* **subscribers**: 구독자 정보를 담고 있습니다. Key-Value 배열 형식으로 구성됩니다. **주소록** **사용자 정의 필드**에 정의된 내용을 따릅니다.\
  \- Key: Key: 사용자 정의 필드의 "태그"(email, name 등)\
  \- Value: Key에 해당하는 값
* Key에 "$ad\_agreed" 필드를 사용해 광고성 정보 수신동의 여부를 구분한다.
  * "Y": 광고성 정보 수신 여부를 '동의함'으로 추가합니다.
  * "N": 광고성 정보 수신 여부를 '동의하지 않음'(빈 값)으로 추가합니다.
  * "$ad\_agreed" 필드를 사용하지 않거나 잘못된 값이 입력된 경우 ‘동의하지 않음’(빈 값)으로 추가합니다. 이때 이미 등록된 구독자의 광고성 정보 수신 동의 여부는 업데이트하지 않습니다.

추가 요청한 구독자가 주소록에 이미 존재하는 이메일 주소인 경우, eventOccuredBy 값과 구독자의 구독 상태에 따라 아래와 같이 처리됩니다.

* **eventOccuredBy가 MANUAL일 때**: 이메일 주소, 이름 등의 구독자 정보를 업데이트합니다. 이 때 구독자의 구독 상태(예. 구독 중, 수신거부)는 변경되지 않습니다.
* **eventOccuredBy가 SUBSCRIBER일 때**: 구독자의 구독 상태에 따라 다르게 처리됩니다.\
  \- **구독 중 상태일 때**: 구독자 정보를 업데이트하지 않습니다. 기존 정보가 그대로 유지됩니다.\
  \- **수신거부 또는 자동삭제 상태일 때**: 구독자의 구독 상태를 구독 중으로 변경하고 이메일 주소, 이름 등의 구독자 정보를 업데이트합니다.

주소록 웹훅으로 "구독" 이벤트 알림을 받기로 한 경우, "confirmEmailYN"이 "Y"라면, 구독 확인까지 완료됐을 때 이벤트 알림을 받을 수 있습니다.\
\
groupId(그룹에 할당된 고유의 아이디)는 아래 방법으로 확인할 수 있습니다.

1. 주소록 목록에서 주소록 이름을 클릭하여 \[주소록 대시보드]로 이동
2. \[그룹]을 클릭하여 그룹 목록으로 이동
3. 그룹 이름을 클릭하여 그룹 필터링이 적용된 구독자 목록으로 이동
4. 브라우저에 표시되는 URL에서 'subscribed' 뒤의 숫자를 확인

&#x20;

<figure><img src="https://help.stibee.com/hc/article_attachments/7000529224847" alt=""><figcaption></figcaption></figure>

이에 대한 응답은 다음과 같습니다.

* **Ok**: 요청에 대한 성공/실패 여부를 구분합니다. (true: 성공, false: 실패)
* **Error**: 요청 실패 원인이 표시됩니다. 에러 코드와 에러 메시지가 표시됩니다.\
  \- code: 에러 코드\
  \- message: 에러 메세지
* **Value**: 요청 성공 결과가 표시됩니다. 결과 유형별로 Key-Value 배열 형식으로 표시됩니다.\
  \- **Key**: 결과 유형\
  \- **success**: 구독자 추가 성공\
  \- **update**: 상태 외 정보 업데이트\
  \- **failNoEmail**: 구독자 추가 실패 - 이메일 주소 없음.\
  \- **failExistEmail**: 구독자 추가 실패 - 이미 구독 중인 이메일 주소\
  \- **failExistPhone**: 구독자 추가 실패 - 이미 구독 중인 전화번호\
  \- **failWrongEmail**: 구독자 추가 실패 - 이메일 주소 형식 오류\
  \- **failWrongPhone**: 구독자 추가 실패 - 전화번호 형식 오류\
  \- **failDuplicatedEmail**: 구독자 추가 실패 - 이메일 주소 중복 요청\
  \- **failDuplicatedPhone**: 구독자 추가 실패 - 전화번호 중복 요청\
  \- **failUnknown**: 구독자 추가 실패 - 알수 없는 오류\
  \- **Value**: Key에 해당하는 구독자 정보가 Key-Value 배열 형식으로 표시됩니다. \[주소록] \[사용자 정의 필드]에 정의된 내용을 참조합니다.\
  \- **Key**: 사용자 정의 필드의 "태그"(email, name 등)\
  \- **Value**: Key에 해당하는 값

&#x20;

### 완전삭제 <a href="#h_bb2bbf9138" id="h_bb2bbf9138"></a>

* **HTTP Methods:** DELETE
* **Endpoint URL:** [https://api.stibee.com/v1/lists/{listid}/subscribers](https://api.stibee.com/v1/lists/%7Blistid%7D/subscribers)

listId(주소록에 할당된 고유의 아이디)는 아래 방법으로 확인할 수 있습니다.

1. 주소록 목록에서 주소록 이름을 클릭하여 \[주소록 대시보드]로 이동
2. 브라우저에 표시되는 URL에서 'lists' 뒤의 숫자를 확인

<figure><img src="https://help.stibee.com/hc/article_attachments/7000529244559" alt=""><figcaption></figcaption></figure>

#### **Request Body**

* 구독자의 이메일 주소를 배열 형식으로 입력합니다. (예: \["[user1@domain.com](mailto:user1@domain.com)","[user2@domain.com](mailto:user2@domain.com)"])&#x20;

이에 대한 응답은 다음과 같습니다.

* **Ok**: 요청에 대한 성공/실패 여부를 구분합니다. (true: 성공, false: 실패)
* **Error**: 요청 실패 원인이 표시됩니다. 에러 코드와 에러 메시지가 표시됩니다.
* **Value**: 요청 성공 결과가 표시됩니다. 결과 유형별로 Key-Value 배열 형식으로 표시됩니다.\
  \- "success": 구독자 완전삭제 성공 리스트\
  \- "fail": 구독자 완전삭제 실패 리스트

&#x20;

### 수신거부 <a href="#h_19b8abd69b" id="h_19b8abd69b"></a>

* **HTTP Methods:** PUT
* **Endpoint URL:** [https://api.stibee.com/v1/lists/{listid}/subscribers/unsubscribe](https://api.stibee.com/v1/lists/%7Blistid%7D/subscribers/unsubscribe)

listId(주소록에 할당된 고유의 아이디)는 아래 방법으로 확인할 수 있습니다.

* 주소록 목록에서 주소록 이름을 클릭하여 “주소록 대시보드"로 이동
* 브라우저에 표시되는 URL에서 "lists" 뒤의 숫자를 확인

<figure><img src="https://help.stibee.com/hc/article_attachments/7000529244559" alt=""><figcaption></figcaption></figure>

#### **Request Body**

* 구독자의 이메일 주소를 배열 형식으로 입력합니다. (예: \["user1@domain.com","user2@domain.com"])

이에 대한 응답은 다음과 같습니다.

* **Ok**: 요청에 대한 성공/실패 여부를 구분합니다. (true: 성공, false: 실패)
* **Error**: 요청 실패 원인이 표시됩니다. 에러 코드와 에러 메시지가 표시됩니다.
* **Value**: 요청 성공 결과가 표시됩니다. 결과 유형별로 Key-Value 배열 형식으로 표시됩니다.\
  \- "success": 구독자 수신거부 성공 리스트\
  \- "failOrAlreadyUnsubscribe": 구독자 실패 또는 이미 수신거부 중 리스트



### 그룹 할당 <a href="#undefined" id="undefined"></a>

* **HTTP Methods:** POST
* **Endpoint URL:** [https://api.stibee.com/v1/lists/{listid}/groups/{groupId}/subscribers/assign](https://api.stibee.com/v1/lists/%7Blistid%7D/groups/%7BgroupId%7D/subscribers/assign)

listId(주소록에 할당된 고유의 아이디)는 아래 방법으로 확인할 수 있습니다.

* 주소록 목록에서 주소록 이름을 클릭하여 “주소록 대시보드"로 이동
* 브라우저에 표시되는 URL에서 "lists" 뒤의 숫자를 확인

<figure><img src="https://help.stibee.com/hc/article_attachments/7000529244559" alt=""><figcaption></figcaption></figure>

groupId(그룹에 할당된 고유의 아이디)는 아래 방법으로 확인할 수 있습니다.

1. 주소록 목록에서 주소록 이름을 클릭하여 \[주소록 대시보드]로 이동
2. \[그룹]을 클릭하여 그룹 목록으로 이동
3. 그룹 이름을 클릭하여 그룹 필터링이 적용된 구독자 목록으로 이동
4. 브라우저에 표시되는 URL에서 'subscribed' 뒤의 숫자를 확인

<figure><img src="https://help.stibee.com/hc/article_attachments/7000529224847" alt=""><figcaption></figcaption></figure>

#### **Request Body**

* 구독자의 이메일 주소를 배열 형식으로 입력합니다. (예: \["[user1@domain.com](mailto:user1@domain.com)","[user2@domain.com](mailto:user2@domain.com)"])&#x20;

이에 대한 응답은 다음과 같습니다.

* **Ok**: 요청에 대한 성공/실패 여부를 구분합니다. (true: 성공, false: 실패)
* **Error**: 요청 실패 원인이 표시됩니다. 에러 코드와 에러 메시지가 표시됩니다.

&#x20;

### 그룹 해제 <a href="#h_01gnrj2avs1qjyd12m26fc47v7" id="h_01gnrj2avs1qjyd12m26fc47v7"></a>

* **HTTP Methods:** POST
* **Endpoint URL**: [https://api.stibee.com/v1/lists/{listid}/groups/{groupId}/subscribers/release](https://api.stibee.com/v1/lists/%7Blistid%7D/groups/%7BgroupId%7D/subscribers/release)

listId(주소록에 할당된 고유의 아이디)는 아래 방법으로 확인할 수 있습니다.

1. 주소록 목록에서 주소록 이름을 클릭하여 “주소록 대시보드"로 이동
2. 브라우저에 표시되는 URL에서 "lists" 뒤의 숫자를 확인

<figure><img src="https://help.stibee.com/hc/article_attachments/7000529244559" alt=""><figcaption></figcaption></figure>

groupId(그룹에 할당된 고유의 아이디)는 아래 방법으로 확인할 수 있습니다.

1. 주소록 목록에서 주소록 이름을 클릭하여 \[주소록 대시보드]로 이동
2. \[그룹]을 클릭하여 그룹 목록으로 이동
3. 그룹 이름을 클릭하여 그룹 필터링이 적용된 구독자 목록으로 이동
4. 브라우저에 표시되는 URL에서 'subscribed' 뒤의 숫자를 확인

&#x20;

<figure><img src="https://help.stibee.com/hc/article_attachments/7000529224847" alt=""><figcaption></figcaption></figure>

#### **Request Body**

* 구독자의 이메일 주소를 배열 형식으로 입력합니다. (예: \["[user1@domain.com](mailto:user1@domain.com)","[user2@domain.com](mailto:user2@domain.com)"])&#x20;

이에 대한 응답은 다음과 같습니다.

* **Ok**: 요청에 대한 성공/실패 여부를 구분합니다. (true: 성공, false: 실패)
* **Error**: 요청 실패 원인이 표시됩니다. 에러 코드와 에러 메시지가 표시됩니다.

_API에 대한 요청 및 응답 방법은_ [_스티비 API 문서_](https://api.stibee.com/docs)_에서 확인하고 테스트해볼 수 있습니다._\
\
_API 요청은 1초당 10회, 1회당 256KB로 제한되어 있습니다._



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

```json
200 OK

{
  "Ok": true,
  "Error": {
    "Code": "string",
    "Message": "string"
  },
  "Value": {} //API 요청에 따라 다른 응답
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

```json
200 OK

{
  "Ok": true,
  "Error": {
    "Code": "string",
    "Message": "string"
  },
  "Value": {} //API 요청에 따라 다른 응답
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
  "Value": "string"
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
      "Message": "Error Message",
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
  "Value": {
    "created_time":"YYYY-MM-DD hh:mm:dd +0900 KST",
    "email":string,
    "modified_time":"YYYY-MM-DD hh:mm:dd +0900 KST",
    "status":string
  }
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

**응답 실패**

```json
400 Bad Request
Content-Type: application/json

{
  "Ok": false,
	  "Error": {
      "Code": "ERR-XXXX",
      "HttpStatusCode": 400,
      "Message": "Error Message",
     }
}
```

* **Ok**: 요청에 대한 성공/실패 유무를 의미합니다. (false: 실패)
* **Error**: 요청 실패 원인이 표시됩니다. 에러 코드와 에러 메시지가 표시됩니다.
  * Code: 에러 코드
  * HttpStatusCode: Http 에러 코드
  * Message: 에러 메시지

구독자 목록 조회의 요청 및 응답 예제는 [여기](api.md#undefined-9)를 참고하세요.

## _AP_I 요청 및 응답 예제

#### 구독자 추가 API 요청 및 응답 예제

“[gildong.go@stibee.com](mailto:gildong.go@stibee.com)”, “[dooly@stibee.com](mailto:dooly@stibee.com)”을 구독 확인 과정 없이 추가할 경우, 다음과 같이 요청합니다.

```json
POST https://api.stibee.com/v1/lists/{listId}/subscribers
[
    {
        "eventOccuredBy": "SUBSCRIBER",
        "confirmEmailYN": "N",
        "groupIds": [
         "{groupId}"
        ],
        "subscribers": [
            {
                "email": "gildong.go@stibee.com",
                "name": "고길동"
            },
            {
                "email": "dooly@stibee.com",
                "name": "둘리"
            }
        ]
    }
]
```

&#x20;

“[gildong.go@stibee.com](mailto:gildong.go@stibee.com)”은 정상적으로 추가됐고, “[dooly@stibee.com](mailto:dooly@stibee.com)”은 수신거부 상태여서 추가되지 않았다면, 이에 대한 응답은 다음과 같습니다.

```json
{
    "Ok": true,
    "Error": null,
    "Value": {
        "failDeny": [
                {
                        "email": "gildong.go@stibee.com",
                        "name": "고길동"
                }
        ],
        "failUnknown": [],
        "failWrongEmail": [],
        "success": [
                {
                        "email": "dooly@stibee.com",
                        "name": "둘리"
                }
        ],
        "update": []
    }
}
```

&#x20;

이미 추가된 "[dooly@stibee.com](mailto:dooly@stibee.com)"의 정보를 변경하려면, "eventOccuredBy"를 "MANUAL"로 설정하여, 다음과 같이 요청합니다.

```json
POST https://api.stibee.com/v1/lists/{listId}/subscribers
[
    {
        "eventOccuredBy": "MANUAL",
        "confirmEmailYN": "N",
        "groupIds": [
         "{groupId}"
        ],
        "subscribers": [
            {
                "email": "dooly@stibee.com",
                "name": "둘리"
            }
        ]
    }
]
```

&#x20;

이미 추가된 '구독중' 상태인 구독자를 "eventOccuredBy"="SUBSCRIBER"로 설정하여 추가 요청하면 추가가 되지 않습니다. 이에 대한 응답은 다음과 같습니다.

```json
{
    "Ok": false,
    "Error":
        {
            "Code": "LIST_ALREADY_SUBSCRIBED",
            "HttpStatusCode": 0,
            "Message": "이미 구독 중인 이메일 주소입니다."
        },
    "Value": null
}
```



#### 주소록 목록 조회 응답 예제

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



#### 그룹 목록 조회 응답 예제

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



#### 구독자 숫자 조회 요청 및 응답 예제

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



#### 구독자 목록 조회 요청 및 응답 예제

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
}
```
