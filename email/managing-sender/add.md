# 발신자 주소 추가하기

## 이 글에서는

가입한 이메일 주소 외에 다른 이메일 주소를 발신자로 설정해 이메일을 보내는 방법을 안내합니다. 발신자 정보의 구성 요소와 설정 방법, 꼭 알아야 할 팁까지 함께 살펴보세요.

***

## 발신자 정보 이해하기

발신자 정보는 이메일을 받은 사람에게 표시되는 보낸 사람 정보를 의미합니다.

예를 들어, 아래 이미지에서 '스티비 팀'은 발신자 이름이고, 'support+seminar@stibee.com'은 발신자 이메일 주소입니다.

<figure><img src="../../.gitbook/assets/발신자 정보 이해하기 (1).png" alt=""><figcaption></figcaption></figure>



## 발신자 이메일 주소 추가하기 <a href="#undefined" id="undefined"></a>

{% hint style="info" %}
[G메일](https://blog.stibee.com/gmail-sender-guidelines/)과 [네이버 메일](https://stibee.com/api/v1.0/emails/share/_pfqzBAjcLjjhSJc5HHpBUUN0W9Mdsc)의 정책에 따라, gmail.com, naver.com 도메인으로 만든 이메일은 발신자 이메일 주소로 설정할 수 없으며, 스티비에서 제공하는 도메인으로 자동 변경되어 저장됩니다.

* example@gmail.com → example-gmali.com@send.stibee.com
* example@naver.com → example-naver.com@send.stibee.com
{% endhint %}

주소록마다 사용할 발신자 이메일 주소를 설정할 수 있습니다.

기본적으로는 워크스페이스 소유자의 이메일 주소가 기본 발신자 이메일 주소로 설정됩니다. 예를 들어, 소유자 이메일 주소가 user@example.com이라면, 모든 주소록의 기본 발신자 주소가 user@example.com으로 설정됩니다.

<figure><img src="../../.gitbook/assets/발신자 추가하기.png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../.gitbook/assets/발신자 추가하기2.png" alt=""><figcaption></figcaption></figure>

발신자 이메일 주소를 추가하는 방법은 아래와 같습니다.

1. \[주소록 → 대시보드]로 이동합니다.
2. \[수정하기]를 클릭해 주소록 정보 수정 화면으로 이동합니다.
3. 발신자 이메일 주소의 \[+추가하기]를 눌러 새로운 발신자 이메일 주소를 입력합니다.
   1. 입력한 이메일 주소로 인증 이메일이 발송되며, 인증을 완료해야 발신자로 사용할 수 있습니다.
4. \[기본값으로 지정하기]를 클릭하면 주소록의 기본 발신자 이메일 주소로 설정되며, 이메일을 새로 만들 때 기본값으로 사용됩니다.
5. \[저장하기]를 클릭해 추가한 정보를 저장합니다.

> **\*주의:** 발신자 이메일 주소를 등록하려면 인증 이메일 수신 및 확인이 필요합니다. 따라서, 실제로 메일을 주고받을 수 있는 이메일 주소만 등록할 수 있습니다.
>
> 회신을 받기 어려운 주소를 사용하는 경우, 이메일 하단에 "해당 발신자 이메일 주소로는 회신을 받지 않습니다." 와 같은 안내 문구를 추가하는 것을 권장드립니다. 스티비에서는 회신을 제한하는 것을 추천하지 않고 있어요. [여기](https://blog.stibee.com/ec-9d-b4-eb-a9-94-ec-9d-bc-ec-a3-bc-ec-86-8c-eb-8a-94-eb-b0-9c-ec-8b-a0-ec-a0-84-ec-9a-a9-ec-a3-bc-ec-86-8c-ec-9e-85-eb-8b-88-eb-8b-a4/)에서 자세한 내용을 살펴보세요.



## 발신자 이름 설정하기 <a href="#undefined" id="undefined"></a>

발신자 이름은 인증 과정 없이 간단하게 설정할 수 있습니다.

* 주소록을 만들거나 수정할 때 기본 발신자 이름을 1개 입력할 수 있습니다.
* 이메일을 만들 때 \[발송 정보] 단계에서 발신자 이름을 자유롭게 수정할 수 있습니다.

주소록에 입력한 발신자 이름은 기본값으로 입력되며, 개별 이메일마다 변경할 수 있습니다.

<figure><img src="../../.gitbook/assets/발신자 이름 설정하기.png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../.gitbook/assets/발신자 이름 설정하기2.png" alt=""><figcaption></figcaption></figure>



## 팁 <a href="#h_73860bb9c5" id="h_73860bb9c5"></a>

* daum.net 등 외부 메일 서비스 도메인보다는 직접 소유한 도메인을 사용하는 것이 좋습니다. 구독자에게 신뢰감을 줄 수 있을 뿐 아니라,[ SPF, DKIM 설정](spf-dkim.md)을 통해 스팸으로 분류될 확률을 낮출 수 있습니다.
* 발신자 정보는 구독자가 이메일을 열지 말지를 판단하는 가장 중요한 요소 중 하나입니다. 회사, 단체, 브랜드 이름이 명확히 드러나는 발신자 이름을 사용하는 것이 좋습니다. 이메일 제목에 담기 어려운 정보는 발신자 이름에 간단히 표현할 수도 있습니다. (예. `스티비 업데이트`, `스티비 뉴스레터`)
