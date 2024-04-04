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

# 발송하기

## 이 글에서는

스티비의 전반적인 이메일 발송 처리 방식에 대해서 알아봅니다.

***

스티비는 안정적인 대량 이메일 발송 처리 시스템을 통해 누구보다 빠르게 이메일을 보낼 수 있습니다. 사용자 환경에서 이메일 발송 요청이 접수되면 내부 처리 엔진을 통해 많은 양도 안정적으로 처리합니다. &#x20;

이메일 발송은 각 구독자 별로 순차적으로 발송이 진행됩니다. 따라서 처음 이메일을 받아보는 구독자와 마지막으로 받아보는 구독자 사이에 시간 차이는 존재합니다. 발송 처리가 모두 완료되는 속도는 발송 성공률에 가장 크게 영향을 받습니다.&#x20;

발송이 실패하는 비율이 높을 수록 시스템에서 자체적으로 재시도를 하는 횟수가 길어지게 되고 이 과정에서 전반적인 발송 완료 속도가 느려질 수 있습니다. 따라서 발송 완료 속도가 고민이라면 발송 성공율 개선을 위한 구독자 정제 작업을 정기적으로 진행해주는 것이 좋습니다.

아래 도움말을 통해 스티비의 전반적인 이메일 발송에 대한 자세한 내용을 학습해보세요.

{% content-ref url="../send/status.md" %}
[status.md](../send/status.md)
{% endcontent-ref %}

{% content-ref url="../send/understand-sending-functionality.md" %}
[understand-sending-functionality.md](../send/understand-sending-functionality.md)
{% endcontent-ref %}

{% content-ref url="../send/spam-rate.md" %}
[spam-rate.md](../send/spam-rate.md)
{% endcontent-ref %}



