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
---

# 발신자 주소 추가하기

## 이 글에서는

가입한 이메일 주소 외에 다른 이메일 주소를 발신자로 설정해 이메일을 보내는 방법을 안내합니다. 발신자 정보의 구성 요소와 설정 방법, 꼭 알아야 할 팁까지 함께 살펴보세요.

***

## 발신자 정보 이해하기

발신자 정보는 이메일을 받은 사람에게 표시되는 보낸 사람 정보를 의미합니다. 예를 들어, 아래 이미지에서 '스티비 팀'은 발신자 이름이고, 'support+seminar@stibee.com'은 발신자 이메일 주소입니다.

<figure><img src="../../.gitbook/assets/발신자 정보 이해하기 (1).png" alt=""><figcaption></figcaption></figure>



## 발신자 이메일 주소 추가하기 <a href="#undefined" id="undefined"></a>

주소록마다 사용할 발신자 이메일 주소를 설정할 수 있습니다. 기본적으로는 워크스페이스 소유자의 이메일 주소가 기본 발신자 이메일 주소로 설정됩니다. 예를 들어, 소유자 이메일 주소가 user@example.com이라면 모든 주소록의 기본 발신자 이메일 주소가 user@example.com으로 설정됩니다.

발신자 이메일 주소를 추가하는 방법은 다음과 같습니다.

1. 발신자 이메일 주소를 추가할 주소록 이름을 클릭합니다.
2. \[대시보드 → 수정하기]를 클릭합니다.
3. \[발신자 이메일 주소 → + 추가하기]를 클릭해 새로운 발신자 이메일 주소를 입력합니다. 인증 이메일이 발송되며, 인증을 완료해야 발신자로 사용할 수 있습니다.
4. \[기본값으로 지정하기]를 클릭하면 해당 주소가 기본 발신자 이메일로 설정되며, 이메일을 새로 만들 때 기본값으로 불러와집니다.
5. \[저장하기]를 클릭합니다.

발신자 이메일 주소는 직접 소유한 도메인(예. stibee.com)으로 만든 주소를 권장합니다. 구독자에게 신뢰감을 줄 수 있고, SPF, DKIM 설정으로 스팸으로 분류될 확률을 낮출 수 있습니다. 자세한 내용은 [나만의 발신자 주소 만들기](https://help.stibee.com/getting-started/preparing-for-start/custom-sender-address) 도움말을 참고해 주세요.

{% hint style="info" %}
인증 이메일 수신이 필요하므로 실제로 메일을 주고받을 수 있는 주소만 등록할 수 있습니다. 회신을 받기 어려운 주소를 사용하는 경우, 이메일 본문에 "해당 발신자 이메일 주소로는 회신을 받지 않습니다."와 같은 안내 문구를 추가하는 것을 권장합니다. 스티비에서는 '발신 전용 이메일 주소' 사용을 권장하지 않습니다. 자세한 내용은 [이 메일주소는 발신전용 주소입니다](https://blog.stibee.com/%EC%9D%B4-%EB%A9%94%EC%9D%BC%EC%A3%BC%EC%86%8C%EB%8A%94-%EB%B0%9C%EC%8B%A0%EC%A0%84%EC%9A%A9-%EC%A3%BC%EC%86%8C%EC%9E%85%EB%8B%88%EB%8B%A4-8f9806db7768) 아티클을 참고해 보세요.
{% endhint %}

<figure><img src="../../.gitbook/assets/발신자 추가하기.png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../.gitbook/assets/발신자 추가하기2.png" alt=""><figcaption></figcaption></figure>



#### gmail.com, naver.com 도메인 주소를 사용하는 경우

현재 G메일과 네이버 메일의 정책에 따라, 외부 서비스에서는 gmail.com, naver.com 도메인을 사용해 이메일을 보낼 수 없습니다. 이 도메인으로 만든 이메일 주소를 발신자로 설정하면, 이메일을 계속 보낼 수 있도록 send.stibee.com 도메인으로 자동 변경되어 저장됩니다. 자동 변경 과정에서 별도의 비용이 발생하지는 않습니다.

* example@gmail.com → example-gmail.com@send.stibee.com
* example@naver.com → example-naver.com@send.stibee.com

다만 send.stibee.com 도메인은 개별 도메인을 준비하기 전까지 사용할 수 있는 대안입니다. 장기적으로 이메일을 보낼 계획이라면, 직접 소유한 도메인으로 발신자 주소를 만드는 것을 권장합니다. 자세한 내용은 [나만의 발신자 주소 만들기](https://help.stibee.com/getting-started/preparing-for-start/custom-sender-address) 도움말을 참고해 주세요.



## 발신자 이름 설정하기 <a href="#undefined" id="undefined"></a>

발신자 이름은 인증 과정 없이 간단하게 설정할 수 있습니다. 주소록에 입력한 발신자 이름은 기본값으로 입력되며, 개별 이메일마다 별도로변경할 수 있습니다.

* 주소록을 만들거나 수정할 때 기본 발신자 이름을 1개 입력할 수 있습니다.
* 이메일을 만들 때 \[발송 정보] 단계에서 발신자 이름을 자유롭게 수정할 수 있습니다.

발신자 정보는 구독자가 이메일을 열지 말지를 판단하는 가장 중요한 요소 중 하나입니다. 회사, 단체, 브랜드 이름이 명확히 드러나는 발신자 이름을 사용하는 것이 좋습니다. 이메일 제목에 담기 어려운 정보는 발신자 이름에 간단히 표현할 수도 있습니다. (예. 스티비 업데이트, 스티비 뉴스레터)

<figure><img src="../../.gitbook/assets/발신자 이름 설정하기.png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../.gitbook/assets/발신자 이름 설정하기2.png" alt=""><figcaption></figcaption></figure>
