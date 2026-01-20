# 구독자를 자동으로 분류하기

## 이 글에서는 <a href="#h_01hh496d5ehdqkmbhd8hamadjq" id="h_01hh496d5ehdqkmbhd8hamadjq"></a>

구독 폼에 파라미터를 추가해 구독자를 특정 그룹으로 자동 분류하거나, 사용자 정의 필드에 원하는 값을 자동으로 입력하는 방법을 안내합니다.

***

## 파라미터 이해하기 <a href="#parameter" id="parameter"></a>

파라미터는 구독 폼 URL 뒤에 특정 값을 추가해 구독 폼의 입력값을 미리 채워두는 기능입니다.&#x20;

파라미터가 없으면 값이 빈 상태로 보이며, 파라미터가 있다면 값이 미리 등록됩니다. 구독자는 자동 입력된 값을 그대로 제출할 수도 있고, 수정해 다른 값을 입력할 수도 있습니다.

#### 예시

구독 폼 URL에 이름(name) 필드를 파라미터로 미리 입력했을 때와 입력하지 않았을 때를 비교해 보면,

* 파라미터가 없는 구독 폼 URL
  * https://page.stibee.com/subscriptions/187957
  * 이름 필드가 비어 있습니다.

<figure><img src="../../.gitbook/assets/파라미터 이해하기_1 (1).png" alt=""><figcaption></figcaption></figure>



* 파라미터가 적용된 구독 폼 URL: https://page.stibee.com/subscriptions/187957?name=스티비
  * 이름 필드에 '스티비'가 자동 입력됩니다.

<figure><img src="../../.gitbook/assets/파라미터 이해하기_2 (1).png" alt=""><figcaption></figcaption></figure>



## 그룹으로 자동 분류하기 <a href="#parameter-group" id="parameter-group"></a>

구독자를 모집할 때, 구독자가 직접 입력하지 않은 정보도 파라미터로 분류할 수 있습니다.

예를 들어, 같은 구독 폼을 여러 SNS에 홍보하는 경우, URL마다 다른 그룹 파라미터를 넣어 유입 경로별 그룹 분류가 가능합니다.

* 페이스북 그룹: https://page.stibee.com/subscriptions/3?groupIds=44737
* 인스타그램 그룹: https://page.stibee.com/subscriptions/3?groupIds=43677

그룹이 삭제되더라도 기존 URL은 계속 사용할 수 있지만, 그룹 자동 분류는 적용되지 않습니다. 그룹과 관련한 자세한 내용은 [그룹 사용하기](../classify-subscribers/how-to-use-groups.md) 도움말을 참고해 주세요.

#### 그룹 ID 확인 방법

1. 주소록 목록에서 원하는 주소록 선택합니다.
2. \[그룹] 메뉴로 이동합니다.
3. 그룹 이름 클릭합니다.
4. 브라우저 URL의 subscribers/S 뒤 숫자 확인합니다.

**\*주의:** groupIds의 I는 영어 대문자 I(아이)입니다.

![](<../../.gitbook/assets/구독자를 자동으로 분류하기_1.png>)



### 스티비 구독 폼 URL에서 그룹 파라미터 사용하기

**\*주의:** groupIds의 I는 영어 대문자 I(아이)입니다.

구독 폼의 URL 형식은 다음과 같습니다.

* https://page.stibee.com/subscriptions/{listid}

특정 그룹에 구독자를 자동 분류하는 URL 형식은 다음과 같습니다.

* https://page.stibee.com/subscriptions/{listid}?groupIds={groupid}

여러 그룹으로 동시에 분류하려면 그룹 파라미터를 여러 개 추가한 뒤, 쉼표로 구분하면 됩니다.

* https://page.stibee.com/subscriptions/{listid}?groupIds={groupid},{groupid}

#### 예시

주소록 listid가 3이고, 그룹 ID가 44737이라면 URL은 다음과 같습니다.

* 일반 구독 폼 URL: https://page.stibee.com/subscriptions/3
* 44737 그룹에 구독자를 추가하는 구독 폼 URL: https://page.stibee.com/subscriptions/3?groupIds=44737
* 44737, 44738 두 개의 그룹에 구독자를 추가하는 구독 폼 URL: https://page.stibee.com/subscriptions/3?groupIds=44737,44738

<figure><img src="../../.gitbook/assets/구독 폼 URL 사용하기.png" alt=""><figcaption></figcaption></figure>



### HTML 코드로 구독 폼을 사용하는 경우 <a href="#html" id="html"></a>

**\*주의:** groupIds의 I는 영어 대문자 I(아이)입니다.

구독 폼 HTML 코드 뒤에 ?groupIds={groupid} 값을 추가합니다.

{% code title="수정 전" overflow="wrap" %}
```
https://stibee.com/api/v1.0/lists/TYW5AcyOVE51JOZtmxyaTL8zPkJ/public/subscribers
```
{% endcode %}

{% code title="수정 후" overflow="wrap" %}
```
https://stibee.com/api/v1.0/lists/TYW5AcyOVE51JOZtmxyaTL8zPkJ/public/subscribers?groupIds={groupid}
```
{% endcode %}

#### 예시

그룹 아이디가 12345인 경우 아래와 같이 url을 수정합니다.

{% code fullWidth="false" %}
```
예시
https://stibee.com/api/v1.0/lists/TYW5AcyOVE51JOZtmxyaTL8zPkJ/public/subscribers?
groupIds=12345
```
{% endcode %}



## 구독자 정보에 자동으로 값 입력하기

구독자를 모집할 때, 구독자가 직접 입력하지 않은 정보도 사용자 정의 필드 파라미터로 자동 수집할 수 있습니다. 사용자 정의 필드의 키(key) 값을 파라미터로 사용하면, 구독 신청 시 해당 값이 자동으로 입력됩니다.

#### field\_key 확인 방법

**\*주의:** field\_key의 I는 영어 대문자 I(아이)입니다.

1. 주소록 목록에서 원하는 주소록을 선택합니다.
2. \[사용자 정의 필드] 메뉴로 이동합니다.
3. 각 필드에 설정된 키(key) 값을 확인합니다. 필요하다면 이 단계에서 사용자 정의 필드를 새로 생성할 수 있습니다.

사용자 정의 필드가 삭제되더라도 기존 URL은 계속 사용할 수 있지만, 사용자 정의 필드 자동 입력은 적용되지 않습니다. 사용자 정의 필드 관련한 자세한 내용은 [구독자 정보 이해하기](../adding-managing-subscriber/understanding-subscriber-info.md) 도움말을 참고해 주세요.&#x20;

### 스티비 구독 폼 URL에서 사용하기

**\*주의:** field\_key의 I는 영어 대문자 I(아이)입니다.

구독 폼의 URL 형식은 다음과 같습니다.

* 일반 구독 폼: https://page.stibee.com/subscriptions/{listid}

사용자 정의 필드 값을 자동 입력하는 URL 형식은 다음과 같습니다.

* https://page.stibee.com/subscriptions/{listid}?field\_key=field\_value

#### 예시

사용자 정의 필드 '유입 경로' 키(key)가 route이고, 값에 stibee를 자동 입력하고 싶다면 다음과 같이 입력해 주세요.

* https://page.stibee.com/subscriptions/3?route=stibee

### HTML 내보내기로 구독 폼을 사용하는 경우

**\*주의:** field\_key의 I는 영어 대문자 I(아이)입니다.

구독 폼 HTML 코드 뒤에 ?field\_key={field\_value} 값을 추가하면 됩니다.

{% code title="수정 전" overflow="wrap" %}
```
https://stibee.com/api/v1.0/lists/TYW5AcyOVE51JOZtmxyaTL8zPkJ/public/subscribers
```
{% endcode %}

{% code title="수정 후" overflow="wrap" %}
```
https://stibee.com/api/v1.0/lists/TYW5AcyOVE51JOZtmxyaTL8zPkJ/public/subscribers
?channel=랜딩페이지
```
{% endcode %}

#### 예시

키(key) 값이 channel인 필드에 'facebook' 값을 자동으로 입력하고 싶다면 아래와 같이 입력합니다.

{% code title="수정 후" overflow="wrap" %}
```
https://stibee.com/api/v1.0/lists/TYW5AcyOVE51JOZtmxyaTL8zPkJ/public/subscribers?channel=facebook
```
{% endcode %}
