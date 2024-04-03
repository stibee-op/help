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

# 발신자 주소 추가하기

## 이 글에서는

발신자 정보를 설정하는 방법에 대해서 알아봅니다. 가입한 이메일 주소 외에 다른 이메일 주소를 발신자로 설정하고 보낼 수 있습니다.

***

발신자 정보는 이메일을 받은 사람에게 표시되는 보낸 사람의 정보를 의미합니다. 발신자 정보는 발신자 이메일 주소와 발신자 이름으로 구성됩니다.&#x20;

<figure><img src="https://help.stibee.com/hc/article_attachments/4756526630159/6270c3665e079.png" alt=""><figcaption></figcaption></figure>

## 발신자 이메일 주소 추가하기 <a href="#undefined" id="undefined"></a>

워크스페이스를 소유한 사용자 이메일 주소를 기본 발신자 이메일 주소로 사용합니다. 예를 들어 user@example.com을 이메일 주소로 사용하는 사용자가 만든 워크스페이스에서는 모든 주소록에서 기본 발신자 주소가 user@example.com으로 설정됩니다. 소유자 이메일 주소 외에 다른 발신자 이메일 주소는 주소록 정보 수정 화면에서 추가할 수 있습니다.

\
주소록 목록에서 주소록 이름을 클릭하여 주소록의 \[구독자 목록]으로 이동합니다.

<figure><img src="https://help.stibee.com/hc/article_attachments/4756471246479/6270c367d3fef.png" alt=""><figcaption></figcaption></figure>

\[대시보드]를 클릭하여 주소록의 대시보드로 이동합니다. 기본 정보 옆의 \[수정하기]를 클릭해 주소록 정보 수정 화면으로 이동합니다.

<figure><img src="https://help.stibee.com/hc/article_attachments/4756471264399/6270c36a082d8.png" alt=""><figcaption></figcaption></figure>

발신자 이메일 주소의 \[+추가하기]를 클릭하면 새 이메일 주소를 입력할 수 있는 메뉴가 표시됩니다. 이메일 주소 인증 과정을 거치기 때문에 실제 이메일을 주고 받을 수 있는 주소만 발신자 이메일 주소로 추가할 수 있습니다. \[기본값으로 지정하기]를 클릭하면 그 이메일 주소가 주소록의 기본 발신자 이메일 주소로 설정되며, 이메일을 만들 때 기본값으로 사용됩니다.

발신자 이메일 주소로 사용하고 싶은 이메일 주소를 등록했다면 주소록의 \[저장하기]를 클릭해 추가한 정보를 저장합니다. 정보를 저장하고 나면 이메일의 \[발송 정보] 단계에서 추가한 발신자 이메일 주소를 선택해 이메일을 보낼 수 있습니다.&#x20;

<figure><img src="https://help.stibee.com/hc/article_attachments/4756471280399/6270c36c8062b.png" alt=""><figcaption></figcaption></figure>

<figure><img src="https://help.stibee.com/hc/article_attachments/4756471308559/6270c36f110ce.png" alt=""><figcaption></figcaption></figure>

\
발신자 이름 설정하기 <a href="#undefined" id="undefined"></a>
----------------------------------------------------

발신자 이름은 인증 과정이 필요하지 않기 때문에 비교적 간단하게 설정할 수 있습니다. 주소록을 만들거나 수정할 때 기본 발신자 이름을 입력합니다. 1개만 입력할 수 있습니다.

<figure><img src="https://help.stibee.com/hc/article_attachments/4756535173647/6270c3734fae5.png" alt=""><figcaption></figcaption></figure>

&#x20;

이메일을 만들 때 \[발송정보]에서 발신자 이름을 변경할 수 있습니다. 주소록에 설정된 발신자 이름 기본값이 입력되어 있고, 이를 얼마든지 수정할 수 있습니다.

<figure><img src="https://help.stibee.com/hc/article_attachments/4756521080463/6270c37631443.png" alt=""><figcaption></figcaption></figure>

## 팁 <a href="#h_73860bb9c5" id="h_73860bb9c5"></a>

* 발신자 이메일 주소로 gmail.com, naver.com 등 외부 이메일 서비스의 도메인을 사용하는 것보다는 본인이 소유한 도메인을 사용하는 것이 좋습니다. 구독자에게 신뢰감을 줄 수 있을 뿐 아니라,[ SPF, DKIM 설정](spf-dkim.md)을 통하여 스팸으로 분류될 확률을 낮출 수 있습니다.
* 발신자 정보는 구독자가 이메일에 대한 신뢰도를 판단하는 가장 중요한 요소입니다.\
  자신이 알고 있고 회원가입을 했거나 수신동의한 회사, 단체, 브랜드 이름을 발신자 이름이나 발신자 이메일 주소의 도메인 주소로 확인할 수 있다면, 신뢰할만한 이메일이라고 판단하고 이메일을 열어보게 됩니다.
* 대부분의 경우, 회사, 단체, 브랜드 이름이 명확하게 드러나는 발신자 이름을 사용합니다. 이메일 제목에 더 많은 내용을 담기 위해, 이메일이나 뉴스레터의 카테고리, 주제 정도를 발신자 이름에 표현하는 경우도 있습니다(예. 스티비 업데이트, 스티비 뉴스레터 등).

