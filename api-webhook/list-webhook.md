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

# 주소록 웹훅

💬 이 내용은 **스탠다드, 프로, 엔터프라이즈 요금제**에 해당하는 도움말입니다.

## 이 글에서는

주소록 웹훅을 사용해 스티비 주소록과 운영하고 있는 DB를 연동하는 방법에 대한 기술적인 설명을 담고 있습니다.

\[주소록 웹훅]은 주소록에서 이벤트가 발생했을 때 사용자의 서버로 알림을 보내주는 기능입니다. 사용자는 어떤 URL로 알림을 받을지, 어떤 내용의 알림을 받을지 설정할 수 있습니다. 알림은 POST Method를 사용하여 JSON 형태로 전달됩니다. 웹훅은 주소록 단위로 관리되며 하나의 주소록은 여러개의 웹훅을 가질 수 있습니다.\
\
주소록 웹훅은 [주소록 API](https://help.stibee.com/hc/ko/articles/4756551371535)와 함께 사용하면 더욱 강력한 기능이 됩니다.

### &#x20; <a href="#h_01ha19g10jfzme0j9g7jn93n5z" id="h_01ha19g10jfzme0j9g7jn93n5z"></a>

## 웹훅 만들기 <a href="#id-1" id="id-1"></a>

웹훅을 사용하려면 우선 스티비에서 웹훅을 만들어야 합니다. 웹훅은 주소록 단위로 관리되기 때문에 웹훅의 생성과 관리는 모두 **웹훅을 사용할 주소록**에서 이루어집니다. **새로 만들기**를 클릭하면 웹훅을 만들 수 있습니다.

<figure><img src="https://help.stibee.com/hc/article_attachments/4756539369615" alt=""><figcaption></figcaption></figure>

웹훅을 만들기 위해 다음의 정보를 입력합니다.

* 이름: 웹훅을 관리하기 위한 이름을 입력합니다.
* URL: 이벤트 알림을 받을 URL을 입력합니다.
* 알림을 받을 이벤트: 알림을 받을 이벤트를 선택합니다. 복수 선택이 가능합니다.

&#x20;

<figure><img src="https://help.stibee.com/hc/article_attachments/4756539403663" alt=""><figcaption></figcaption></figure>

**주소록** **웹훅**에서 생성된 웹훅을 확인하고, 웹훅을 활성화, 비활성화, 수정, 삭제할 수 있습니다.

<figure><img src="https://help.stibee.com/hc/article_attachments/4756530846863" alt=""><figcaption></figcaption></figure>

웹훅에는 별도의 인증 과정이 없기 때문에, 인증이 필요한 경우 스티비의 웹훅 서버의 IP 주소로 인증 처리를 해야 합니다. 스티비의 웹훅 서버의 IP 주소는 다음과 같습니다.

* 52.78.132.66

&#x20;

## 이벤트 종류 <a href="#id-2" id="id-2"></a>

웹훅에서 알림을 받을 수 있는 이벤트의 종류는 다음과 같습니다.

* **구독**: 주소록에 구독자가 추가됐습니다.
* **구독자 정보 변경**: 구독자의 정보(이름 등)가 변경됐습니다.
* **수신거부**: 구독자가 수신거부 상태로 변경됐습니다.
* **수신거부 취소**: 구독자의 수신거부가 취소됐습니다.
* **자동삭제**: 구독자가 자동삭제 상태로 변경됐습니다.
* **완전삭제**: 구독자가 완전삭제됐습니다.

모든 이벤트는 관리자 또는 API를 통해 발생하거나 구독자에 의해 발생했을 수 있습니다. 이에 대한 정보는 별도의 String으로 전달됩니다.

&#x20;

## 이벤트 모델 <a href="#id-3" id="id-3"></a>

웹훅 알림은 POST Method를 사용하여 JSON 형식으로 전달됩니다. 전달되는 이벤트 모델의 기본 구조는 다음과 같습니다.

_\*웹훅 요청이 실패하는 경우 자동으로 웹훅 요청에 대하여 3회 재시도 처리를 진행합니다._

&#x20;

### id <a href="#id" id="id"></a>

주소록의 고유 아이디입니다.

### action <a href="#action" id="action"></a>

발생한 이벤트의 종류입니다.

* "SUBSCRIBED": 구독
* "UPDATED": 구독자 정보 변경
* “UNSUBSCRIBED”: 수신거부
* “RESUBSCRIBED”: 수신거부 취소
* “DELETED”: 자동삭제
* “PURGED”: 완전삭제

### eventOccuredBy <a href="#eventoccuredby" id="eventoccuredby"></a>

이벤트를 발생시킨 주체입니다.

* “MANUAL”: 관리자 또는 API에 의해 발생
* “SUBSCRIBER”: 구독자에 의해 발생

### subscribers <a href="#subscribers" id="subscribers"></a>

구독자 정보를 담고 있습니다. Key-Value 배열 형식으로 구성됩니다. **주소록** **사용자 정의 필드**에 정의된 내용을 참조합니다. 이벤트 종류에 따라 추가 정보를 표시합니다.

* Key: 사용자 정의 필드의 “태그”(email, name 등)
* Value: Key에 해당하는 값. 구독, 구독자 정보 변경 이벤트 발생 시에만 \[사용자 정의 필드]에 정의된 내용이 포함되며, 나머지 이벤트에 대해서는 “email” 값만 표시됩니다.

이벤트 종류에 따라 아래 정보가 추가됩니다.

* "UPDATED"(구독자 정보 변경): "old\_email": "구독자가 변경 전 사용하던 이메일 주소"
* “UNSUBSCRIBED”(수신거부): "$unsubscribe\_reason": "구독자가 수신거부 화면에서 입력한 수신거부 사유"&#x20;

단, \[사용자 정의 필드]에 "old\_email"이라는 키 값을 사용하는 필드가 있다면, 이전에 사용하던 이메일 주소가 아닌 사용자 정의 필드의 값이 표시됩니다. (old\_email 값이 제대로 표시되기 위해 사용자 정의 필드에 old\_email 키 값의 필드가 있다면 키 값을 수정해주세요.)

&#x20;

## 이벤트 예제 <a href="#id-4" id="id-4"></a>

구독자가 구독 신청 양식을 통해 직접 구독한 경우, 다음과 같은 이벤트 알림이 전달됩니다.

```json
{
    "id":"4617",
    "action":"SUBSCRIBED",
    "eventOccuredBy":"SUBSCRIBER",
    "subscribers": [
        {"email":"gildong@stibee.com", "name":"길동"}
    ]
}
```

\
구독자가 수신거부한 경우, 다음과 같은 이벤트 알림이 전달됩니다.

```json
{
    "id":"4617",
    "action":"UNSUBSCRIBED",
    "eventOccuredBy":"SUBSCRIBER",
    "subscribers": [
        {"email":"gildong@stibee.com", "$unsubscribe_reason": "수신거부 사유"}
    ]
}
```

\
스티비에서 관리자가 여러명의 구독자를 한 번에 추가한 경우, 다음과 같은 이벤트 알림이 전달됩니다.

```json
{
    "id":"4617",
    "action":"SUBSCRIBED",
    "eventOccuredBy":"MANUAL",
    "subscribers": [
        {"email":"gildong@stibee.com", "name":"길동"}
        {"email":"dooly@stibee.com", "name":"둘리"}
        {"email":"doner@stibee.com", "name":"도우너"}
    ]
}
```

&#x20;

구독자가 정보를 직접 변경한 경우, 다음과 같은 이벤트 알림이 전달됩니다.

```json
{
    "id":"4617",
    "action":"UPDATED",
    "eventOccuredBy":"SUBSCRIBER",
    "subscribers": [
        {"email":"gildong@stibee.com", "old_email":"gildong@naver.com"}
    ]
}
```

&#x20;

관리자가 구독자의 정보를 변경한 경우, 다음과 같은 이벤트 알림이 전달됩니다.

```json
{
    "id":"4617",
    "action":"UPDATED",
    "eventOccuredBy":"MANUAL",
    "subscribers": [
        {"email":"gildong@stibee.com", "old_email":"gildong@naver.com"}
    ]
}
```

\
