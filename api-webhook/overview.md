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

💬 이 내용은 **스탠다드, 프로, 엔터프라이즈 요금제**에 해당하는 도움말입니다.

## 이 글에서는

스티비가 제공하는 API와 웹훅 기능에 관해 알아봅니다.

***

## 스티비 API 이해하기

스티비 API를 사용하면 내가 가진 운영 DB 또는 앱(서비스)과 스티비를 연동해 사용할 수 있습니다. 가지고 있는 고객 DB를 주소록에 연동해서 사용하거나 발송한 이메일의 통계를 스티비에 로그인하지 않고 외부에서 확인하고 싶은 경우 등 다양한 방식으로 스티비를 활용할 수 있습니다. 예를 들면,

* 가지고 있는 DB와 주소록을 연동하여 사용할 수 있습니다.
* 발송한 이메일의 통계를 외부에서 조회하고 원하는 방식으로 대시보드를 구성해 관리할 수 있습니다.
* 서비스에서 특정 이벤트가 발생했을 때마다 자동으로 설정해둔 이메일을 보낼 수 있습니다.&#x20;

이 외에도 스티비 API를 사용하면 더 다양한 시나리오를 자유롭게 구성하여 활용할 수 있기 때문에 더 확장된 기능을 경험할 수 있습니다.



## 스티비 웹훅

웹훅을 사용하면 주소록에서 이벤트가 발생했을 때 내 서버로 알림을 받아볼 수 있습니다. 웹훅을 사용하면 주소록에서 업데이트 된 구독자의 정보, 수신거부 여부 등을 내 DB에도 반영할 수 있습니다. 예를 들면,&#x20;

* 스티비로 보낸 이메일을 dooly@stibee.com 구독자가 수신거부한 경우 내 DB에도 dooly@stibee.com 회원의 이메일 수신 여부를 업데이트 할 수 있습니다.
* [구독 정보 변경 화면](../page/subscriber-guide/modify.md) 에서 구독자가 직접 자신의 정보를 수정한 경우 내 DB에도 수정 내용을 업데이트 할 수 있습니다.
* 주소록에서 gildong.go@stibee.com 구독자를 삭제한 경우 내 DB에서도 완전히 삭제할 수 있습니다.

'[주소록 - 구독자 API](https://stibeev2.apidocumentation.com/docs#tag/%EC%A3%BC%EC%86%8C%EB%A1%9D---%EA%B5%AC%EB%8F%85%EC%9E%90/POST/lists/{id}/subscribers)'와 웹훅을 함께 사용하면 내 DB와 주소록을 완전히 동기화하여 사용할 수 있습니다.



## 섹션 살펴보기

이번 API, 웹훅 세션에서는 API와 웹훅의 사용 방법에 관해 살펴봅니다. API 키 발급 등 기본적인 사용 방법은 도움말을 참고하고, 구체적인 요청 및 응답 방법은 [스티비 API 문서](https://developers.stibee.com)를 참고해 주세요. 웹훅의 기본 사용 방법과 구체적인 요청 및 응답은 '웹훅 사용하기' 도움말을 참고해 주시면 됩니다.

{% content-ref url="api.md" %}
[api.md](api.md)
{% endcontent-ref %}

{% content-ref url="list-webhook.md" %}
[list-webhook.md](list-webhook.md)
{% endcontent-ref %}
