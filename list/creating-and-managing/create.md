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

# 주소록 만들기

## 이 글에서는

구독자를 추가하고, 관리할 수 있는 일반 주소록의 기본 사용 방법에 대해 알아봅니다.

***

\[주소록]은 구독자의 이메일 주소와 정보가 저장되는 곳입니다. 이메일을 보내기 위해서는 이메일을 받아볼 수신자를 주소록에 구독자로 추가해야 합니다. 주소록을 만들면 구독자를 추가하거나 관리할 수 있고, 추가한 구독자는 목적에 따라 \[[세그먼트](../classify-subscribers/how-to-use-segment.md)]나 \[[그룹](../classify-subscribers/how-to-use-groups.md)]으로 분류해서 이메일을 보낼 수 있습니다.&#x20;



## 주소록 만들기 <a href="#h_01gf88hr2750sqpb51k4xxdbj7" id="h_01gf88hr2750sqpb51k4xxdbj7"></a>

1. 메인 화면의 \[주소록]을 클릭합니다.
2. 여기서 \[새로 만들기 → 일반 주소록]을 클릭합니다.

일반 주소록을 클릭하면 주소록 생성 화면으로 이동합니다. 주소록 생성 화면에서 '주소록 이름, 기본 발신자 이름, 발신자 이메일 주소, 이메일 푸터 정보, 자동 삭제 기능 사용 유무'를 설정할 수 있습니다.&#x20;

<figure><img src="../../.gitbook/assets/일반 주소록 만들기.png" alt=""><figcaption></figcaption></figure>

\[주소록 이름]은 주소록을 관리하기 위한 용도로 사용됩니다. 설정한 주소록 이름은 [수신거부 페이지](../../email/edit/unsubscribe.md)나 [구독 폼](../gather-subscribers/form.md) 통해 구독자에게 표시될 수 있으니 적절한 이름으로 수정하는 것이 좋습니다.

\[기본 발신자 이름]은 이메일을 만들 때 불러오는 발신자 이름의 기본값입니다.

<figure><img src="../../.gitbook/assets/주소록 설정.png" alt=""><figcaption></figcaption></figure>



## 발신자 이메일 주소 추가하기 <a href="#h_01gf88jfx86w5ewkkk27bdp48j" id="h_01gf88jfx86w5ewkkk27bdp48j"></a>

가입한 이메일 주소 외에 다른 이메일 주소를 추가해서 발신자 주소로 사용할 수 있습니다. 여기서 추가한 발신자 이메일 주소는 \[발송 정보] 단계에서 선택할 수 있습니다. 기본 발신자 이메일 주소로 설정하면 이메일을 만들 때 자동으로 해당 이메일 주소가 불러와집니다. _발신자 이메일 주소는 최대 5개까지 추가할 수 있습니다._

1. 발신자 이메일 주소를 추가하고 싶은 \[주소록]을 선택합니다.
2. \[대시보드 → 수정하기]를 누릅니다.
3. \[발신자 이메일 주소 → + 추가하기]를 클릭해서 발신자 이메일 주소를 추가할 수 있습니다. 이때, 이메일 주소 인증 과정을 거치기 때문에 실제 이메일을 주고받을 수 있는 주소만 발신자 이메일 주소로 추가할 수 있습니다.
4. \[기본값으로 지정]을 누르면 추가한 이메일 주소를 '기본 발신자 이메일 주소'로 설정할 수 있습니다.

{% hint style="info" %}
스티비에서는 '발신 전용 이메일 주소' 사용은 권장하지 않고 있습니다. 발신 전용 이메일 주소를 권장하지 않는 이유는 [이 메일주소는 발신전용 주소입니다.](https://blog.stibee.com/%EC%9D%B4-%EB%A9%94%EC%9D%BC%EC%A3%BC%EC%86%8C%EB%8A%94-%EB%B0%9C%EC%8B%A0%EC%A0%84%EC%9A%A9-%EC%A3%BC%EC%86%8C%EC%9E%85%EB%8B%88%EB%8B%A4-8f9806db7768) 블로그 아티클을 참고해 보세요.
{% endhint %}

<figure><img src="../../.gitbook/assets/발신자 주소 추가.png" alt=""><figcaption></figcaption></figure>



## 푸터 정보 설정하기

\[이메일 푸터 정보]에서 회사명 또는 이름, 주소, 전화번호 등 이메일 본문 하단에 들어갈 푸터 정보를 설정할 수 있습니다.

**\*주의**: 정보통신망법에 따라 '광고성 정보'를 보내는 경우 반드시 전송자 정보를 이메일 안에 포함해야 합니다.

<figure><img src="../../.gitbook/assets/푸터 정보 추가.png" alt=""><figcaption></figcaption></figure>

## 자동삭제 기능 사용 여부 설정하기 <a href="#auto-deletion" id="auto-deletion"></a>

이메일 마케팅에서는 이메일 발송에 실패하는 경우를 '[바운스](../../email/analytics/email-detailed-statistics.md#h_01gfmfz4vxk1e8gds0mhbttyrm)'라고 표현합니다. 이메일을 영구적으로 수신할 수 없는 상태의 구독자는 하드바운스로 분류되며, 자동삭제 됩니&#xB2E4;_._

자동삭제 기능은 기본적으로 켜져 있습니다. 만약, 구독자를 자동으로 삭제하고 싶지 않다면 \[자동삭제 기능을 사용하시겠습니까? → 아니요]를 선택해 주세요.

자동삭제 기능을 설정하면 이메일 주소가 비활성화되는 등 이메일 수신이 불가능한 상태인 구독자가 자동으로 걸러지므로 일반적으로 발송 성공률이 높아집니다. 특별한 경우가 아니라면 자동삭제 기능 사용을 추천드립니다. _자동삭제 상태의 구독자는 주소록에서 삭제되는 것은 아니며, \[구독 상태 필터 → 자동삭제]를 통해 대상을 확인할 수 있습니다._

발송 실패에 대한 자세한 내용은 [#bounce](../../email/analytics/email-detailed-statistics.md#bounce "mention") 도움말을 참고해 주세요.

<figure><img src="../../.gitbook/assets/주소록 만들기_자동삭제.png" alt=""><figcaption></figcaption></figure>

## 수신거부 구독자 발송 대상 포함 여부 설정하기

보내는 이메일의 성격이나 목적에 따라 수신거부 구독자에게도 발송할 수 있는 이메일이 있습니다. \[수신거부 구독자를 발송 대상에 포함할 수 있게 하시겠습니까? → 예]를 선택하면 수신거부 구독자도 발송 대상에 포함하여 이메일을 보낼 수 있습니다.&#x20;

**\*주의:** \[예]를 선택하는 경우 수신거부 상태인 구독자도 전체 구독자 수 계산에 포함됩니다. 이때 사용하는 구간에 따라 추가 요금이 발생할 수 있으니 유의하세요.

자세한 내용은 아래 도움말을 참고해 보세요.

{% content-ref url="../../email/send/send-email-unsubscribed-subscriber.md" %}
[send-email-unsubscribed-subscriber.md](../../email/send/send-email-unsubscribed-subscriber.md)
{% endcontent-ref %}

<figure><img src="../../.gitbook/assets/주소록 만들기_수신거부.png" alt=""><figcaption></figcaption></figure>



모든 정보를 입력하고 옵션을 선택한 뒤 \[저장하기]를 클릭하면 새로운 주소록이 만들어집니다.
