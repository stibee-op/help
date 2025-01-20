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

이메일을 받아본 구독자가 수신을 거부하고 싶은 경우 스티비의 '수신거부' 기능을 사용하면 자동으로 주소록에서 구독자의 상태가 '수신거부'로 변경되도록 설정할 수 있습니다. '수신거부' 상태인 구독자는 자동으로 이메일 발송 대상에서 제외되고 요금 구간 선택을 위한 구독자 수 계산에서도 제외됩니다. 이 도움말에서는 이메일에 구독자가 수신거부를 할 수 있는 링크를 넣는 방법에 대해 알아봅니다.

***

## 수신거부 기능 이해하기 <a href="#h_2055ad7d04" id="h_2055ad7d04"></a>

이메일 본문이나 구독 정보 변경 페이지에 있는 수신거부 링크를 클릭하는 경우 구독자는 아래와 같은 화면으로 이동합니다. 여기서 \[수신거부 하기] 버튼을 클릭하면 그 구독자는 '[구독 상태](../../list/adding-managing-subscriber/understanding-subscriber-status.md)'가 수신거부 상태로 변경되며 발송 대상에서 자동으로 제외됩니다.

<figure><img src="../../.gitbook/assets/image (18) (1).png" alt=""><figcaption></figcaption></figure>



## 수신거부 기능 사용하기 <a href="#h_ae2d2b0813" id="h_ae2d2b0813"></a>

### 콘텐츠 에디터에서 수신거부 링크 넣기 <a href="#h_ae2d2b0813" id="h_ae2d2b0813"></a>

이메일을 새로 만들거나 수정할 때 \[콘텐츠] 단계에서 \[푸터 상자]를 추가하면 수신거부 링크를 넣을 수 있습니다. 상자의 '수신거부, Unsubscribe'  텍스트에 자동으로 수신거부 링크가 추가되어있습니다. 수신거부 링크가 꼭 푸터 상자의 형태로 추가되어야 하는 것은 아닙니다. 다른 텍스트, 이미지, 버튼에도 수신거부 링크를 추가할 수 있습니다. 수신거부 링크를 추가할 텍스트, 이미지, 버튼을 선택하고 툴바에서 링크 아이콘을 클릭합니다. 링크 입력창 오른쪽에 있는 중괄호 ( { } ) 버튼을 클릭하고 \[수신거부]를 선택하면 자동으로 수신거부 치환자 링크($%unsubscribe%$)가 삽입됩니다.

\***주의**: 수신거부 치환자 링크가 아닌 다른 링크를 넣어 보내는 경우에는 수신거부 기능이 동작하지 않습니다.

<figure><img src="../../.gitbook/assets/image (19) (1).png" alt=""><figcaption></figcaption></figure>



### HTML 코드로 편집할 때도 수신거부 링크 넣기  <a href="#h_99886c447f" id="h_99886c447f"></a>

HTML 코드를 사용해 이메일을 편집할 때도 수신거부 링크를 넣을 수 있습니다. 자세한 사용 방법은 [#unsubscribe](../undefined-1/html.md#unsubscribe "mention")도움말을 참고해 주세요.



수신거부 된 구독자는 이메일이 발송된 주소록에서 확인할 수 있습니다. 수신거부 하려는 구독자에게 수신을 거부하는 이유도 입력 받을 수 있습니다. 관련해 자세한 내용은 [수신거부 관리하기](../../list/adding-managing-subscriber/manage-unsubscribe.md) 도움말에서 확인해 보세요.
