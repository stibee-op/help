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

# 카페24

## 이 글에서는

카페24와 스티비를 연동하고, 이 연동을 해제하는 방법에 관해 알아봅니다.

***

카페24에서 스티비 앱을 설치하면 카페24 연동 주소록이 생성되며, 카페24 쇼핑몰 회원 정보를 카페24 연동 주소록에 실시간으로 연동합니다.

* 스티비 ↔ 카페24 연동은 쇼핑몰과 주소록을 1:1로 연동하는 방식입니다. 카페24 연동 주소록은 최대 15개까지 만들 수 있습니다.
* 스티비 주소록에서 카페24 회원을 완전 삭제할 수 없으며, 구독 상태(수신거부, 수신거부 취소하기)를 변경할 수 없습니다.&#x20;
  * 카페24 연동 주소록과 연결된 구독 폼을 통해 직접 구독 신청한 구독자나 관리자가 주소록에 직접 추가한 구독자만 삭제할 수 있습니다.
* 카페24 회원 중 이메일 수신에 동의한 회원만 연동 주소록에 '구독 중' 상태로 추가됩니다. 이메일 수신에 동의하지 않은 회원은 '수신거부' 상태로 추가됩니다. 수신거부 상태인 구독자는 구독자 수 계산에서 제외되며, 과금 기준에도 포함되지 않습니다.
* 이메일 수신에 동의하던 회원이 이메일에서 수신 거부하면, 카페24 회원 DB에도 수신 거부 상태가 반영됩니다.

아래 도움말을 참고해 카페24와 스티비를 연동해 보세요. 언제든지 연동을 해제할 수도 있습니다.

{% content-ref url="how-to-integration.md" %}
[how-to-integration.md](how-to-integration.md)
{% endcontent-ref %}

{% content-ref url="undefined.md" %}
[undefined.md](undefined.md)
{% endcontent-ref %}

{% content-ref url="disconnect.md" %}
[disconnect.md](disconnect.md)
{% endcontent-ref %}
