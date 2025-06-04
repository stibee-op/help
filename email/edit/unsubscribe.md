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

# 수신거부 링크 추가하기

## 이 글에서는

구독자가 수신 거부할 수 있는 링크를 이메일 본문에 넣는 방법을 알아봅니다.

***

## 수신거부 기능 이해하기 <a href="#h_2055ad7d04" id="h_2055ad7d04"></a>

스티비의 '수신거부' 기능을 사용하면, 구독자가 수신거부를 요청할 경우 구독 상태가 자동으로 ‘수신거부’로 변경됩니다. 수신거부 처리된 구독자는 이후 발송 대상에서 자동 제외되며, 요금 구간 계산 기준에도 포함되지 않습니다.

이메일 본문 또는 구독 정보 변경 페이지에 있는 \[수신거부] 링크를 클릭하면 구독자는 수신거부 화면으로 이동하며, 여기서 \[수신거부하기] 버튼을 누르면 즉시 처리됩니다.

<figure><img src="../../.gitbook/assets/수신거부1 (1).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../.gitbook/assets/수신거부2.png" alt=""><figcaption></figcaption></figure>



수신거부 처리가 완료되면 아래 정보가 화면에 표시됩니다.

* 수신거부 처리된 날짜 및 시간
* 수신거부 처리된 주소록 이름
* 수신거부 처리 결과

<figure><img src="../../.gitbook/assets/수신거부3.png" alt=""><figcaption></figcaption></figure>



\[다시 구독하기]를 눌러 다시 구독 신청을 진행할 수 있습니다.

<figure><img src="../../.gitbook/assets/수신거부4 (1).png" alt=""><figcaption></figcaption></figure>



## 수신거부 링크 추가하기

스티비의 수신거부 링크는 치환자($%unsubscribe%$) 형태로 제공됩니다. 이 치환자를 이메일에 넣으면, 발송 시 구독자마다 맞춤형 수신거부 링크로 자동 바뀌어 전달됩니다.&#x20;

**\*주의:** 치환자 형태가 아닌 일반 링크를 넣으면 수신거부 기능이 작동하지 않습니다.



### 푸터 상자 추가하기

오른쪽 상자 목록에서 \[푸터] 상자를 추가해 주세요. 상자의 '수신거부, Unsubscribe' 텍스트에 수신거부 링크가 치환자 형태로 추가되어 있습니다.

### 직접 입력하기

텍스트, 이미지, 버튼 등에 수신거부 링크를 추가할 수 있습니다.

1. 수신거부 링크를 추가하고 싶은 요소를 선택합니다.
2. 툴바의 \[링크] 아이콘을 클릭합니다.
3. 링크 입력창 오른쪽에 있는 \[중괄호 {  }]버튼 버튼을 누르고 \[수신거부 URL]을 선택하면, 수신거부 치환자가 추가됩니다.

<figure><img src="../../.gitbook/assets/수신거부5.png" alt=""><figcaption></figcaption></figure>

### HTML 코드로 편집할 때도 수신거부 링크 넣기  <a href="#h_99886c447f" id="h_99886c447f"></a>

HTML 코드를 사용해 이메일을 편집할 때도 수신거부 링크를 넣을 수 있습니다. 자세한 사용 방법은 [#unsubscribe](../undefined-1/html.md#unsubscribe "mention")도움말을 참고해 주세요.



주소록에서 수신거부 상태의 구독자를 확인할 수 있습니다. 또한, 수신거부를 원하는 구독자로부터 수신거부 이유도 입력받을 수 있습니다. 자세한 내용은 [수신거부 관리하기](../../list/adding-managing-subscriber/manage-unsubscribe.md) 도움말에서 확인해 보세요.
