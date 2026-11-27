---
layout:
  width: default
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
  metadata:
    visible: true
  tags:
    visible: true
  actions:
    visible: true
  anchors:
    visible: true
---

# 수신거부 관리하기

## 이 글에서는 <a href="#h_01hgacv5bwpkqwdremqhm44cwv" id="h_01hgacv5bwpkqwdremqhm44cwv"></a>

수신거부는 구독자가 이메일을 더 이상 받고 싶지 않을 때 직접 수신을 거부하는 기능입니다. 수신거부한 구독자를 확인하고 관리하는 방법을 알아봅니다.

{% hint style="info" %}
수신거부 기능은 이메일에 메일머지 치환자를 넣어 사용합니다. 자세한 내용은 [수신거부 링크 추가하기](../../email/edit/unsubscribe.md) 도움말을 참고해 주세요.
{% endhint %}

***

## 수신거부 목록 확인하기 <a href="#h_4854aebca7" id="h_4854aebca7"></a>

구독자가 수신을 거부하면 주소록에서 구독 상태가 '수신거부'로 변경됩니다.

1. \[주소록]에서 확인하고 싶은 주소록을 선택한 뒤, \[구독자 목록]을 클릭합니다.
2. 구독 상태 필터에서 \[수신거부]를 선택합니다.

이메일별로 수신거부한 구독자는 [이메일 상세 통계](../../email/analytics/email-statistics-dashboard.md#h_b39175c058)에서 확인할 수 있습니다.

<figure><img src="../../.gitbook/assets/수신거부 목록 조회.png" alt=""><figcaption></figcaption></figure>

### 수신거부로 변경하거나 취소하기 <a href="#h_744c2fd03e" id="h_744c2fd03e"></a>

구독 중인 구독자를 수신거부 상태로 바꾸거나, 수신거부한 구독자를 다시 구독 중으로 바꿀 수 있습니다.

1. \[주소록]에서 주소록을 선택한 뒤, \[구독자 목록]을 클릭합니다.
2. 상태를 바꿀 구독자를 선택합니다.
3. \[상태 변경하기]를 클릭한 뒤, \[수신거부로 변경하기] 또는 \[수신거부 취소하기]를 선택합니다.

여러 구독자의 상태를 한 번에 바꿀 때는 아래 내용을 확인해 주세요.

* 수신거부 취소하기: 한 번에 최대 20명까지 진행할 수 있습니다.
* 수신거부로 변경하기: 인원이 많다면 \[파일로 추가하기]를 사용합니다. 자세한 방법은 [파일로 추가할 때 수신거부 상태로 추가하기](add.md#h_01gfam9r8typybhwpebnjf382c) 도움말을 참고해 주세요.

<div><figure><img src="../../.gitbook/assets/수신거부로 변경하기_1.png" alt=""><figcaption></figcaption></figure> <figure><img src="../../.gitbook/assets/spaces_eAMHRdY4ATDXfWZWQs3p_uploads_c0i5DJlWmqm6QClSiFhN_수신거부로 변경하기_2.webp" alt=""><figcaption></figcaption></figure></div>

### 수신거부 적용 범위 이해하기

수신거부는 주소록 단위로 적용됩니다. 수신거부는 주소록 단위로 적용됩니다. 예를 들어 dooly@stibee.com 구독자가 A 주소록과 B 주소록에 모두 있고, A 주소록으로 보낸 이메일에서 수신거부했다면 다음과 같이 처리됩니다.

* A 주소록: 구독 상태가 '수신거부'로 변경됩니다.
* B 주소록: 구독 상태가 '구독 중'으로 유지됩니다.

구독자를 쉽게 관리하려면 주소록을 하나만 사용하는 것을 권장합니다. 구독자를 나눠 관리하고 싶다면 [그룹](../classify-subscribers/how-to-use-groups.md) 또는 [세그먼트](../classify-subscribers/how-to-use-segment.md) 기능을 활용해 주세요.



## 수신거부 이유 입력받기 <a href="#h_50529e632a" id="h_50529e632a"></a>

구독자가 수신을 거부할 때 그 이유를 입력받을 수 있습니다. 이 기능을 켜면 수신거부 화면에 이유를 입력하는 창이 표시됩니다. 이유는 주관식으로 최대 50자까지 입력할 수 있습니다.

1. \[주소록]에서 주소록을 선택한 뒤, \[구독 화면]으로 이동합니다.
2. 화면 아래 \[수신거부 화면]에서 \[수신거부 이유 입력받기]를 켭니다.

구독자가 입력한 이유는 아래에서 확인할 수 있습니다.

* 구독자 한 명씩 확인하기: \[구독자 대시보드 → 활동]
* 한 번에 모아서 확인하기: \[주소록 → 구독자 목록 → 내보내기]로 내려받은 파일

<figure><img src="../../.gitbook/assets/2 (6).png" alt=""><figcaption></figcaption></figure>



## 수신거부 화면 언어 설정하기 <a href="#h_01hgaf2jgtj77h3jbpjm6hxh4v" id="h_01hgaf2jgtj77h3jbpjm6hxh4v"></a>

수신거부 화면에 표시되는 언어는 \[주소록 → 구독 화면 → 수신거부 화면 → 언어]에서 바꿀 수 있습니다. 기본 언어는 '한국어+영어'이며, '영어' 또는 '일본어'로 변경할 수 있습니다.

<figure><img src="../../.gitbook/assets/수신거부 화면 언어 설정하기.png" alt=""><figcaption></figcaption></figure>



이메일의 성격이나 목적에 따라 수신거부한 구독자에게도 보낼 수 있는 이메일이 있습니다. 자세한 내용은 [수신거부 구독자에게 이메일 보내기](../../email/send/send-email-unsubscribed-subscriber.md) 도움말을 참고해 주세요.
