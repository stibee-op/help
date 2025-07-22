# 수신거부 관리하기

## 이 글에서는 <a href="#h_01hgacv5bwpkqwdremqhm44cwv" id="h_01hgacv5bwpkqwdremqhm44cwv"></a>

수신 거부된 구독자를 관리하는 방법에 대해서 알아봅니다.

{% hint style="info" %}
스티비에서는 구독자가 이메일을 더 이상 받아보고 싶지 않을 때 수신을 거부할 수 있는 \[수신거부] 기능을 제공합니다. 수신거부는 이메일에 특정 치환자 링크를 넣는 것으로 사용할 수 있습니다. 이메일에 수신거부 링크를 넣는 방법은 [unsubscribe.md](../../email/edit/unsubscribe.md "mention") 도움말을 참고해 주세요.
{% endhint %}

***

## 수신거부 목록 확인하기 <a href="#h_4854aebca7" id="h_4854aebca7"></a>

구독자가 이메일에서 수신 거부하면 수신 거부한 이메일이 발송된 주소록에 수신거부 상태로 분류됩니다.&#x20;

1. 수신거부 목록을 확인하고 싶은 \[주소록]을 선택한 뒤, \[구독자 목록]을 클릭합니다.
2. 구독 상태 필터에서 \[수신거부]를 선택하면 수신 거부된 구독자 명단을 확인할 수 있습니다.

[이메일 상세 통계](../../email/analytics/email-detailed-statistics.md)에서 이메일별로 어떤 구독자가 수신거부를 했는지 명단을 확인할 수도 있습니다.

<figure><img src="../../.gitbook/assets/수신거부 목록 조회.png" alt=""><figcaption></figcaption></figure>

### 수신거부로 변경하거나 취소하기 <a href="#h_744c2fd03e" id="h_744c2fd03e"></a>

{% hint style="info" %}
한 번에 최대 20명까지의 구독자만 \[수신거부 취소하기]를 진행할 수 있습니다. 또한, \[파일로 추가하기]를 통해 \[수신거부 취소하기] 처리는 불가합니다.
{% endhint %}

수신거부 상태의 구독자를 다시 구독 중으로 변경하거나 혹은 구독 중 상태인 구독자를 수신거부 상태로 직접 변경할 수 있습니다.

1. 수신거부 목록을 확인하고 싶은 \[주소록]을 선택한 뒤, \[구독자 목록]을 클릭합니다.
2. 수신거부로 변경하거나 취소하고 싶은 구독자를 주소록에서 선택한 뒤, \[상태 변경하기 → 수신거부로 변경하기 또는 수신거부 취소하기]를 클릭합니다.
3. 구독자의 구독 상태가 변경됩니다.

한 번에 여러 명의 구독자를 수신거부 상태로 변경하려면 파일로 추가하기 기능을 사용해야 합니다. 자세한 방법은 [#h\_01gfam9r8typybhwpebnjf382c](add.md#h_01gfam9r8typybhwpebnjf382c "mention") 도움말을 참고해 주세요.

<div><figure><img src="../../.gitbook/assets/수신거부로 변경하기_1.png" alt=""><figcaption></figcaption></figure> <figure><img src="../../.gitbook/assets/spaces_eAMHRdY4ATDXfWZWQs3p_uploads_c0i5DJlWmqm6QClSiFhN_수신거부로 변경하기_2.webp" alt=""><figcaption></figcaption></figure></div>

### 사용 시 주의사항 <a href="#h_744c2fd03e" id="h_744c2fd03e"></a>

수신거부 기능을 포함한 구독자 정보는 주소록 단위로 적용됩니다.

예를 들어 dooly@stibee.com 구독자가 A 주소록과 B 주소록에 각각 추가되어 있고, A 주소록으로 발송한 이메일에서 수신거부를 진행했다면,

* A 주소록에서 dooly@stibee.com 구독자의 구독 상태는 \[수신거부]로 변경됩니다.
* B 주소록에서 dooly@stibee.com 구독자의 구독 상태는 \[구독 중]으로 유지됩니다.

손쉬운 구독자 관리를 위해 되도록 하나의 주소록을 사용하시는 걸 권장드립니다. 만약, 특정 기준으로 구독자를 분류해서 관리하고 싶다면 [그룹](../classify-subscribers/how-to-use-groups.md) 또는 [세그먼트](../classify-subscribers/how-to-use-segment.md) 기능 활용을 추천드립니다.



## 수신거부 이유 입력받기 <a href="#h_50529e632a" id="h_50529e632a"></a>

구독자가 수신을 거부하는 이유를 입력받을 수 있습니다. 수신거부 이유 입력받기 기능이 켜져 있는 상태라면 수신거부 화면에 이유를 입력할 수 있는 창이 표시됩니다. _수신거부 사유는 주관식으로만 입력할 수 있고, 최대 50자까지 작성할 수 있습니다._

1. 수신거부 이유를 입력받고 싶은 \[주소록]을 선택한 뒤, \[구독 화면]으로 이동합니다.
2. \[구독 화면]에서 아래로 내려가면 \[수신거부 화면]이 나타납니다.
3. \[수신거부 이유 입력받기] 버튼을 클릭해서 기능을 켜거나 끌 수 있습니다.

구독자가 입력한 수신거부 사유는 구독자별 활동 기록 화면에서 확인할 수 있습니다. 또는 \[주소록 → 구독자 목록 → 내려받기]를 통해 내려받은 [구독자 목록](export-list.md)이나 [구독자별 통계](../check-subscriber-statistics/export.md) 파일에서 수신거부 사유를 확인할 수 있습니다.

<figure><img src="../../.gitbook/assets/2 (6).png" alt=""><figcaption></figcaption></figure>



## 수신거부 화면 언어 설정하기 <a href="#h_01hgaf2jgtj77h3jbpjm6hxh4v" id="h_01hgaf2jgtj77h3jbpjm6hxh4v"></a>

언어는 기본적으로 '한국어+영어'가 표시되도록 설정되어 있습니다. 표시되는 언어를 '영어' 또는 '일본어'로 표시되도록 하려면 사용할 언어를 수정해 주시면 됩니다.

\[주소록 → 구독 화면 → 수신 거부 화면 → 언어]에서 수신거부 화면에 표시되는 언어를 설정할 수 있습니다.&#x20;

<figure><img src="../../.gitbook/assets/수신거부 화면 언어 설정하기.png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
보내는 이메일의 성격 또는 목적에 따라 수신거부 구독자에게도 발송할 수 있는 이메일이 있습니다. 수신거부 구독자에게도 이메일을 보내는 방법이 궁금하다면 [수신거부 구독자에게 이메일 보내기](../../email/send/send-email-unsubscribed-subscriber.md) 도움말을 참고하세요.
{% endhint %}
