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

# 구독자를 자동으로 분류하기

## 이 글에서는 <a href="#h_01hh496d5ehdqkmbhd8hamadjq" id="h_01hh496d5ehdqkmbhd8hamadjq"></a>

구독 폼 URL에 특정 파라미터를 추가하면 구독자를 자동으로 원하는 \[그룹]으로 분류하도록 할 수 있고 사용자 정의 필드에 원하는 정보를 등록해 특정 \[세그먼트]로 자동 분류되도록 할 수 있습니다. 그 방법에 대해 알아봅니다.

***

## 파라미터 이해하기 <a href="#parameter" id="parameter"></a>

그룹으로 특정 구독자를 분류하거나 구독자 정보에 특정 값이 자동으로 입력되게 하려면 우선 파라미터의 개념을 알아두는 것이 좋습니다.

파라미터란, URL에 특정한 형식을 넣어 미리 값이 적용될 수 있도록 하는 기능을 의미합니다. 파라미터가 없는 경우에는 값이 빈 상태로 보여지며, 파라미터가 있다면 값이 미리 등록됩니다. (파라미터로 값이 미리 등록되어 있어도 값을 바꾸면 바꾼 값으로 저장됩니다.)  구독 폼 URL에 이름 필드(name)를 파라미터로 미리 입력했을 때와 입력하지 않았을 때의 차이를 아래 URL을 통해서 확인할 수 있습니다.



**파라미터가 적용되지 않은 구독 폼 URL**

```
https://page.stibee.com/subscriptions/187957
```

<figure><img src="../../.gitbook/assets/파라미터 이해하기_1 (1).png" alt=""><figcaption></figcaption></figure>



**파라미터가 적용된 구독 폼 URL**

```
https://page.stibee.com/subscriptions/187957?name=스티비
```

<figure><img src="../../.gitbook/assets/파라미터 이해하기_2 (1).png" alt=""><figcaption></figcaption></figure>



## 그룹으로 자동 분류하기 <a href="#parameter-group" id="parameter-group"></a>

### 스티비 구독 폼을 사용하는 경우 <a href="#parameter-group-form" id="parameter-group-form"></a>

구독 폼 URL 뒤에 'groupIds(대소문자 구분)'라는 파라미터를 추가하면 구독자가 추가될 그룹을 지정할 수 있습니다. 그룹에 할당된 고유 아이디(group id)는 아래 방법으로 확인할 수 있습니다.

1. 주소록 목록에서 주소록 이름을 클릭하여 \[주소록 대시보드]로 이동
2. \[그룹]을 클릭하여 그룹 목록으로 이동
3. \[그룹] 이름을 클릭하여 그룹 필터링이 적용된 구독자 목록으로 이동
4. 브라우저에서 표시되는 URL에서 'subscribers/S' 뒤의 숫자를 확인

![](<../../.gitbook/assets/구독자를 자동으로 분류하기\_1.png>)

\[구독 폼] URL은 아래의 형식으로 만들어집니다.

* 일반 구독 폼 URL 형식: https://page.stibee.com/subscriptions/{listid}&#x20;
* 그룹에 구독자를 추가하는 구독 폼 URL 형식: https://page.stibee.com/subscriptions/{listid}?groupIds={groupid}

_\*groupIds의 I는 영어 대문자 I(아이)입니다._

예를 들어, 스요레터 주소록의 listid는 3이고, groupId는44737 인그룹에 구독자를 자동으로 추가하고 싶다면, 아래 형식으로 구독 폼 URL을 만들 수 있습니다.

* 스요레터 구독 폼 URL: https://page.stibee.com/subscriptions/3
* 스요레터 주소록의 44737 그룹에 구독자를 추가하는 구독 폼 URL: https://page.stibee.com/subscriptions/3?groupIds=44737

한 번에 여러 개의 그룹에 추가하려면, 쉼표(,)로 구분하여 'groupIds' 파라미터를 여러 개 추가하면 됩니다. 예를 들어, 44737과 44738 그룹에 구독자를 한 번에 추가하고 싶다면, 아래 형식으로 만들면 됩니다. \
_\* groupIds의 I는 영어 대문자 I(아이)입니다._

* _https://page.stibee.com/subscriptions/{listid}**?groupIds={groupid},{groupid}**_
* _예. https://page.stibee.com/subscriptions/3?groupIds=44737,44738_



### HTML 내보내기로 구독 폼을 사용하는 경우 <a href="#html" id="html"></a>

구독 폼을 코드로 내보낸 뒤에, 코드에서 일부 내용을 수정해 사용하면 됩니다. 구독 폼 코드에서 아래 형식의 코드를 찾습니다.

{% code title="수정 전" overflow="wrap" %}
```
https://stibee.com/api/v1.0/lists/OOOOOOOOOOOOOOO/TYW5AcyOVE51JOZtmxyaTL8zPkJ/public/subscribers
```
{% endcode %}

이 주소 뒤에 ?groupIds={groupid} 값을 추가하면 됩니다. 예를 들어, 그룹의 아이디가 12345인 경우 아래와 같이 url을 수정합니다.

{% code title="수정 후" overflow="wrap" %}
```
https://stibee.com/api/v1.0/lists/OOOOOOOOOOOOOOO/TYW5AcyOVE51JOZtmxyaTL8zPkJ/public/subscribers?groupIds=12345
```
{% endcode %}





### 페이지를 사용하는 경우 <a href="#page" id="page"></a>

\[[페이지](broken-reference)]로 구독 신청을 받는 경우에도 페이지 URL 뒤에 그룹 코드를 추가하면 구독자를 그룹으로 자동 분류할 수 있습니다. 페이지 URL은 아래의 형식으로 생성됩니다.

* https://{subdomain}.stibee.com/
* 예. https://syoletter.stibee.com/

이 URL 뒤에 아래의 형식으로 "groupIds"(대소문자 구분)라는 파라미터를 추가하면 그룹을 지정할 수 있습니다.&#x20;

_\*"groupIds"의 "I"는 대문자 "I"(아이)입니다._

* https://{subdomain}.stibee.com/**?groupIds={groupid}**
* 예: https://syoletter.stibee.com/?groupIds=44737

한 번에 여러개의 그룹에 추가하려면, 쉼표(,)로 구분하여 "groupIds" 파라미터를 여러 개 추가하면 됩니다. \*"groupIds"의 "I"는 대문자 "I"(아이)입니다.

* https://{subdomain}.stibee.com/**?groupIds={groupid},{groupid}**
* 예: https://syoletter.stibee.com/?groupIds=44737,44738



이 기능을 사용하면 구독 신청을 받을 때 구독자가 직접 입력하지 않은 정보를 수집할 수 있습니다. 가령, 구독자를 모으기 위해 구독 폼 URL을 여러 SNS 채널에 홍보한다고 가정합니다. 유입 경로별로 그룹을 만들고(예. 페이스북, 인스타그램, 블로그), 동일한 구독 폼에 대해 각 그룹별 파라미터를 추가해 사용하면, 유입 경로에 따라 서로 다른 그룹에 구독자를 추가할 수 있습니다.



## 구독자 정보에 자동으로 값 입력하기

사용자 정의 필드 파라미터를 구독 폼, 페이지 등의 URL에 추가하면 특정 구독자 정보를 자동으로 추가할 수 있습니다.

### 스티비 구독 폼을 사용하는 경우 <a href="#h_56b1e65f3d" id="h_56b1e65f3d"></a>

구독 폼 URL은 아래의 형식으로 생성됩니다.

* [https://page.stibee.com/subscriptions/{listid}](https://page.stibee.com/subscriptions/%7Blistid%7D)
* 예. [https://page.stibee.com/subscriptions/3](https://page.stibee.com/subscriptions/3)

이 URL 뒤에 아래의 형식으로 "사용자 정의 필드의 키 값"을 추가하면 구독 시 구독자 정보에 원하는 값이 자동으로 입력되도록 설정할 수 있습니다.

* [https://page.stibee.com/subscriptions/{listid}](https://page.stibee.com/subscriptions/%7Blistid%7D)**?field\_key={field\_value}**
* 예. [https://page.stibee.com/subscriptions/3?route=stibee](https://page.stibee.com/subscriptions/3?route=stibee)

field\_key는 사용자 정의 필드의 키 값으로 주소록 내 사용자 정의 필드에서 확인할 수 있습니다.

<figure><img src="https://downloads.intercomcdn.com/i/o/525689679/c19b573c5f701291070f790d/%EC%82%AC%EC%9A%A9%EC%9E%90%EC%A0%95%EC%9D%98%ED%95%84%EB%93%9C%ED%8C%8C%EB%9D%BC%EB%AF%B8%ED%84%B0_3.gif" alt=""><figcaption></figcaption></figure>



### HTML 내보내기로 구독 폼을 사용하는 경우

구독 폼을 코드로 내보낸 뒤에, 코드에서 일부 내용을 수정해 사용하면 됩니다. 구독 폼 코드에서 아래 형식의 코드를 찾습니다.

{% code title="수정 전" overflow="wrap" %}
```
https://stibee.com/api/v1.0/lists/OOOOOOOOOOOOOOO/TYW5AcyOVE51JOZtmxyaTL8zPkJ/public/subscribers
```
{% endcode %}

이 주소 뒤에 ?field\_key={field\_value} 값을 추가하면 됩니다. 예를 들어, Key 값이 channel인 필드에 '랜딩페이지'라는 값을 자동으로 입력하고 싶다면 아래와 같이 입력합니다.

{% code title="수정 후" overflow="wrap" %}
```
https://stibee.com/api/v1.0/lists/OOOOOOOOOOOOOOO/TYW5AcyOVE51JOZtmxyaTL8zPkJ/public/subscribers?channel=랜딩페이지
```
{% endcode %}



### 페이지를 사용하는 경우

페이지 URL은 아래의 형식으로 생성됩니다.

* [https://{subdomain}.stibee.com](https://{subdomain}.stibee.com/)
* 예. [https://syoletter.stibee.com](https://syoletter.stibee.com/subscribe/)

이 URL 뒤에 아래의 형식으로 "사용자 정의 필드의 키 값"을 추가하면 구독 시 구독자 정보에 원하는 값이 자동으로 입력되도록 설정할 수 있습니다.

* [https://{subdomain}.stibee.com](https://{subdomain}.stibee.com/)**?field\_key={field\_value}**
* 예. [https://syoletter.stibee.com?route=stibee](https://page.stibee.com/subscriptions/3?route=stibee)

{% hint style="info" %}
* 사용자 정의 필드에 없는 필드를 파라미터로 넣는 경우 정보가 입력되지 않습니다.
* 구독 폼에서 파라미터로 설정한 필드의 값을 구독자가 변경하는 경우 변경된 값으로 정보가 입력됩니다.
{% endhint %}

