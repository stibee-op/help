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

# 페이지 URL 그룹 파라미터 사용하기

## 이 글에서는

페이지 URL 뒤에 그룹 코드를 추가하면 구독자를 그룹으로 자동 분류할 수 있습니다. 이 방법에 관해 알아봅니다.

그룹을 만들고 관리하는 방법 [how-to-use-groups.md](../../list/classify-subscribers/how-to-use-groups.md "mention") 도움말을 참고해 주세요. 구독자 정보가 사용자 정의 필드에 자동으로 입력되도록 설정하고 싶다면, [#undefined](../../list/gather-subscribers/automated-categorization.md#undefined "mention") 도움말을 참고해 주세요.

***

## 페이지 URL 그룹 파라미터 사용하기

페이지 URL은 아래의 형식으로 만들어집니다.&#x20;

* 형식: https://{subdomain}.stibee.com
* 예: https://newsletter.stibee.com

이 URL 뒤에 아래의 형식으로 groupIds(대소문자 구분함) 파라미터를 추가하면 그룹을 지정할 수 있습니다.&#x20;

**\*주의:** groupIds의 'I'는 대문자 'I(아이)'입니다.&#x20;

* 형식: https://{subdomain}.stibee.com/**?groupIds={groupid}**
* 예: https://syoletter.stibee.com/**?groupIds=44737**

groupId(그룹에 할당된 고유 아이디)는 아래 방법으로 확인할 수 있습니다.&#x20;

1. \[주소록 → 그룹]으로 이동합니다.
2. 구독자를 분류할 그룹을 선택한 뒤, 브라우저에 표시되는 URL에서 'subscribers/S' 뒤의 숫자를 확인합니다. 이 숫자가 그룹의 고유 아이디입니다.

<figure><img src="../../.gitbook/assets/4 (15).png" alt=""><figcaption></figcaption></figure>

한 번에 여러 개의 그룹에 추가하려면, 쉼표(,)로 구분하여 groupIds 파라미터를 여러 개 추가하면 됩니다.

**\*주의:** groupIds의 'I'는 대문자 'I(아이)'입니다.&#x20;

* 형식: https://{subdomain}.stibee.com/**?groupIds={groupid},{groupid}**
* 예: https://syoletter.stibee.com/**?groupIds=44737,44738**

이 기능을 사용하면 구독 신청을 받을 때 구독자로부터 정보를 직접 입력받지 않아도 추가적인 정보를 수집할 수 있습니다.

예를 들어 구독자를 모으기 위해 페이지 URL을 여러 채널에 홍보한다고 가정하면, 유입 경로별로 그룹을 여러 개 만든 뒤(예: 페이스북, 인스타그램 등) 그룹별 파라미터를 추가해서 사용하면 유입 경로에 따라 구독자를 각기 다른 그룹에 추가할 수 있습니다.
