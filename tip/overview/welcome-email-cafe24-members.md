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

# 카페24 회원에게 웰컴 이메일 보내기

💬 이 내용은 **스탠다드, 프로, 엔터프라이즈 요금제**에 해당하는 도움말입니다.

## 언제 필요한가요?

* 카페24 ↔ 스티비 연동 기능을 사용하면서 가입 환영 이메일을 보내고 싶은 경우

***

스티비 [자동 이메일](welcome-email-cafe24-members.md#h\_01hrecxeytk4f2xvsx27gstdaa) 기능과 [연동 주소록](../../integration/cafe24/)을 함께 사용하면, 카페24 쇼핑몰에 새로 가입한 회원에게 자동으로 웰컴 이메일을 보낼 수 있습니다. 웰컴 이메일은 쇼핑몰에 회원 가입한 것을 환영하는 이메일입니다. 웰컴 이메일은 다른 종류의 이메일보다 오픈율이 최대 3배까지 높으므로 이 이메일만 잘 설정하면 앞으로 발송할 이메일의 성과를 크게 개선할 수 있습니다.



## 카페24 쇼핑몰과 주소록 연동하기 <a href="#h_01hre9s9frgdt1zdnfkq19p2fb" id="h_01hre9s9frgdt1zdnfkq19p2fb"></a>

카페24 회원에게 자동으로 웰컴 이메일을 보내고 싶다면, 먼저 카페24 쇼핑몰과 스티비 주소록을 연동해야 합니다. 카페24 스토어에서 스티비 앱을 설치하면 연동이 완료됩니다. 아직 \[카페24 연동 주소록]이 생성되지 않았다면 [카페24 연동하기](../../integration/cafe24/) 도움말을 참고해서 연동을 완료해 주세요.

&#x20;

## 자동 이메일 만들기 <a href="#h_01hrecxeytk4f2xvsx27gstdaa" id="h_01hrecxeytk4f2xvsx27gstdaa"></a>

화면 위쪽 \[이메일]을 누른 뒤, \[새로 만들기 → 자동 이메일]을 클릭해 \[자동 이메일]을 만듭니다.

![](https://help.stibee.com/hc/article\_attachments/9192762183439)

주소록 선택 단계에서 \[카페24 연동 주소록]을 선택하세요.&#x20;

<figure><img src="https://help.stibee.com/hc/article_attachments/9192793872271" alt=""><figcaption></figcaption></figure>

주소록을 선택했다면, 이제 자동 이메일이 발송될 조건을 설정할 차례입니다. \[발송조건] 단계에서 트리거를 \[구독자 추가]로 선택합니다. \[구독자 추가]로 선택하면 카페24 연동 주소록에 회원이 새롭게 추가될 때마다 자동으로 이메일이 발송됩니다.&#x20;

_\* 다른 트리거에 대한 자세한 설명은_ [_여기_](https://help.stibee.com/hc/ko/articles/4756530141583)_를 참고해 주세요._&#x20;

<figure><img src="https://help.stibee.com/hc/article_attachments/9192894765327" alt=""><figcaption></figcaption></figure>

이때, 구독 폼을 통해 구독을 신청한 구독자나 직접 추가한 구독자에게는 웰컴 이메일을 보내지 않고 싶다면, 필터에서 '카페24 회원 여부 → 회원입니다.'를 선택해 주세요. 카페24 쇼핑몰의 '회원가입' 기능을 사용해 가입한 회원에게만 웰컴 이메일이 발송됩니다.&#x20;

<figure><img src="https://help.stibee.com/hc/article_attachments/9193047358991" alt=""><figcaption></figcaption></figure>

<figure><img src="https://help.stibee.com/hc/article_attachments/9192894767375" alt=""><figcaption></figcaption></figure>

발송정보 단계에서 이메일 제목, 발신자 이름, 발신자 이메일 주소, 미리보기 텍스트를 설정합니다.&#x20;

<figure><img src="https://help.stibee.com/hc/article_attachments/9190670342031" alt=""><figcaption></figcaption></figure>

이제는 이메일을 만들 차례입니다. 미리 제공된 템플릿을 선택해서 편집해도 좋고, 처음부터 이메일을 만들어도 좋습니다. 이때, 이메일 제목이나 본문에 [메일머지](../../email/edit/personalized-merge.md) 기능을 활용해 구독자의 이름을 불러주는 등 더 개인화된 이메일을 보낼 수 있습니다.&#x20;

![](https://help.stibee.com/hc/article\_attachments/9193116344975)

어떤 식으로 구성을 해야 할지 고민된다면 [스티비 블로그](https://blog.stibee.com/welcome-email/)를 참고해 보세요. 이메일을 편집하는 방법에 대한 자세한 설명은 [스티비 시작하기](../../getting-started/send-first-email.md#undefined-2)에서 확인하세요. 이메일 편집을 완료했다면 화면 오른쪽 위의 \[시작하기] 버튼을 눌러 자동 이메일을 발송할 수 있는 상태로 만듭니다.\
\
_\*자동 이메일이 '실행 중' 상태가 아니라면 설정한 발송 조건을 만족해도 이메일이 발송되지 않습니다._

![](https://help.stibee.com/hc/article\_attachments/9193038631055)

\[시작하기]를 클릭하면 자동 이메일이 '실행중' 상태로 변경됩니다. 메인 메뉴 중 \[이메일]을 클릭해서 자동이메일의 상태를 확인할 수 있습니다.&#x20;
