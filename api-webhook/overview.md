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

# 개요

## 이 글에서는

스티비가 제공하는 API와 웹훅 기능에 관해 살펴보고 섹션의 구성에 관해 알아봅니다.

***

## API 이해하기

서로 다른 애플리케이션 간에 데이터를 주고받으며 서로 연동할 수 있도록 돕는 규약을 일컬어 API라고 부릅니다. 스티비가 제공하는 여러 API와 웹훅 기능을 활용하면 더욱 확장된 기능을 경험할 수 있습니다.



### 주소록 API <a href="#h_01hrp917a0eyb3pcjd1crr02jk" id="h_01hrp917a0eyb3pcjd1crr02jk"></a>

내 서비스의 회원 정보를 스티비 주소록과 연동해서 사용하고 싶다면 '주소록 API'를 활용해 보세요. 주소록 API를 사용하면 내 서비스에 새로운 회원이 가입할 때 연동된 스티비 주소록에 자동으로 추가하거나 기존 회원의 정보가 변경됐을 때 자동으로 연동된 스티비 주소록의 정보도 함께 업데이트하는 등 보다 확장된 기능을 경험할 수 있습니다.

_\* '주소록 API'는 '주소록 웹훅'과 함께 사용하면 내 서비스의 회원 DB와 스티비 주소록을 완전히 동기화해서 사용할 수 있어요._



### 이메일 조회 API

'이메일 목록'과 각 이메일의 '[상세 통계](../email/analytics/email-detailed-statistics.md)'를 외부에서 조회하고 활용하고 싶다면 '이메일 조회 API'를 활용해 보세요.&#x20;



### 자동 이메일 API

자동 이메일이 발송될 조건을 API로 직접 요청하고 싶다면, '자동 이메일 API'를 활용하면 됩니다. 내부에 개발 여력이 존재한다면 이 기능을 사용해서 다양한 자동 이메일 발송 시나리오를 구현할 수 있습니다.

예를 들어, 비밀번호 재설정을 요청한 고객에게 임시 비밀번호가 적힌 자동 이메일을 보낼 수 있습니다. 또는 장바구니에 물건을 담아두고 N일이 경과했지만 구매하지 않은 고객에게 구매를 유도하기 위한 마케팅 이메일을 보내볼 수도 있습니다.



## 웹훅 이해하기

서로 다른 애플리케이션 간에 이벤트 기반 통신을 가능하게 하는 방법을 일컬어 웹훅이라고 부릅니다. 특정 이벤트가 발생하면 다른 애플리케이션에 데이터를 자동으로 전송할 수 있는 기능입니다.



### 주소록 웹훅

\[주소록 웹훅]은 주소록에서 이벤트가 발생했을 때 사용자의 서버로 알림을 보내주는 기능입니다. 어떤 URL로 알림을 받을지, 어떤 내용의 알림을 받을지 설정하실 수 있습니다.&#x20;

_\* '주소록 웹훅'은 '주소록 API'과 함께 사용하면 내 서비스의 회원 DB와 스티비 주소록을 완전히 동기화해서 사용할 수 있어요._



## 섹션 살펴보기

아래 도움말을 참고해 스티비가 제공하는 API, 웹훅 기능을 활용할 수 있습니다.

{% content-ref url="list-api.md" %}
[list-api.md](list-api.md)
{% endcontent-ref %}

{% content-ref url="list-webhook.md" %}
[list-webhook.md](list-webhook.md)
{% endcontent-ref %}

{% content-ref url="email-retrieval-api.md" %}
[email-retrieval-api.md](email-retrieval-api.md)
{% endcontent-ref %}

{% content-ref url="auto-email-api.md" %}
[auto-email-api.md](auto-email-api.md)
{% endcontent-ref %}
