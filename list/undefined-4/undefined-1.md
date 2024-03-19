# 구독자를 자동으로 분류하기

## 구독 신청한 구독자를 그룹으로 자동 분류하기: 구독 폼 URL 파라미터

### 이 글에서는 <a href="#h_01hh496d5ehdqkmbhd8hamadjq" id="h_01hh496d5ehdqkmbhd8hamadjq"></a>

\[구독 폼] URL 뒤에 [그룹](https://help.stibee.com/hc/ko/articles/4756567819791) 코드를 추가하면 구독자를 그룹으로 자동 분류할 수 있습니다. 스티비 \[[구독 폼](https://help.stibee.com/hc/ko/articles/4756470653199)]을 사용해 구독자를 수집하거나 \[[HTML 내보내기](https://help.stibee.com/hc/ko/articles/4756475522703)]를 통해 외부 페이지서 구독자 정보를 수집하는 경우 '둘 다 사용 가능'합니다. 그 사용 방법을 알아봅니다.

&#x20;

### 목차 <a href="#h_01hh496d5enrvdrh3c4k4zc1nq" id="h_01hh496d5enrvdrh3c4k4zc1nq"></a>

[스티비 구독 폼을 사용하는 경우](https://help.stibee.com/hc/ko/articles/4756482888463-%EA%B5%AC%EB%8F%85-%EC%8B%A0%EC%B2%AD%ED%95%9C-%EA%B5%AC%EB%8F%85%EC%9E%90%EB%A5%BC-%EA%B7%B8%EB%A3%B9%EC%9C%BC%EB%A1%9C-%EC%9E%90%EB%8F%99-%EB%B6%84%EB%A5%98%ED%95%98%EA%B8%B0-%EA%B5%AC%EB%8F%85-%ED%8F%BC-URL-%ED%8C%8C%EB%9D%BC%EB%AF%B8%ED%84%B0#-----)\
[HTML 내보내기로 구독 폼을 사용하는 경우](https://help.stibee.com/hc/ko/articles/4756482888463-%EA%B5%AC%EB%8F%85-%EC%8B%A0%EC%B2%AD%ED%95%9C-%EA%B5%AC%EB%8F%85%EC%9E%90%EB%A5%BC-%EA%B7%B8%EB%A3%B9%EC%9C%BC%EB%A1%9C-%EC%9E%90%EB%8F%99-%EB%B6%84%EB%A5%98%ED%95%98%EA%B8%B0-%EA%B5%AC%EB%8F%85-%ED%8F%BC-URL-%ED%8C%8C%EB%9D%BC%EB%AF%B8%ED%84%B0#html----)

&#x20;

### 스티비 구독 폼을 사용하는 경우 <a href="#undefined" id="undefined"></a>

\[구독 폼] URL은 아래의 형식으로 만들어집니다. 구독 폼 URL 뒤에 'groupIds(대소문자 구분)'라는 파라미터를 추가하면 구독자가 추가될 그룹을 지정할 수 있습니다. _\* groupIds의 I는 영어 대문자 I(아이)입니다._

* 일반 구독 폼 URL 형식: https://page.stibee.com/subscriptions/{listid}
* 그룹에 구독자를 추가하는 구독 폼 URL 형식: https://page.stibee.com/subscriptions/{listid}?groupIds={groupid}

예를 들어, 스요레터 주소록의 listid는 3이고, 44737 그룹에 구독 신청하는 구독자를 자동으로 추가하고 싶다면, 아래 형식으로 구독 폼 URL을 만들 수 있습니다.

* 스요레터 구독 폼 URL: https://page.stibee.com/subscriptions/3
* 스요레터 주소록의 44737 그룹에 구독자를 추가하는 구독 폼 URL: https://page.stibee.com/subscriptions/3?groupIds=44737

그룹에 할당된 고유 아이디(group id)는 아래 방법으로 확인할 수 있습니다.

1. 주소록 목록에서 주소록 이름을 클릭하여 \[주소록 대시보드]로 이동
2. \[그룹]을 클릭하여 그룹 목록으로 이동
3. \[그룹] 이름을 클릭하여 그룹 필터링이 적용된 구독자 목록으로 이동
4. 브라우저에서 표시되는 URL에서 'subscribers/S' 뒤의 숫자를 확인

![stibee-help-group\_id.png](https://help.stibee.com/hc/article\_attachments/5749074065167)

&#x20;

한 번에 여러 개의 그룹에 추가하려면, 쉼표(,)로 구분하여 'groupIds' 파라미터를 여러 개 추가하면 됩니다. 예를 들어, 44737과 44738 그룹에 구독자를 한 번에 추가하고 싶다면, 아래 형식으로 만들면 됩니다. _\* groupIds의 I는 영어 대문자 I(아이)입니다._

* _https://page.stibee.com/subscriptions/{listid}**?groupIds={groupid},{groupid}**_
* _예. https://page.stibee.com/subscriptions/3?groupIds=44737,44738_

이 기능을 사용하면 구독 신청을 받을 때 구독자가 직접 입력하지 않은 정보를 수집할 수 있습니다. 가령, 구독자를 모으기 위해 구독 폼 URL을 여러 SNS 채널에 홍보한다고 가정합니다. 유입 경로별로 그룹을 만들고(예. 페이스북, 인스타그램, 블로그), 동일한 구독 폼에 대해 각 그룹별 파라미터를 추가해 사용하면, 유입 경로에 따라 서로 다른 그룹에 구독자를 추가할 수 있습니다.

&#x20;

### HTML 내보내기로 구독 폼을 사용하는 경우 <a href="#html" id="html"></a>

구독 폼을 코드로 내보낸 뒤에, 코드에서 일부 내용을 수정해 사용하면 됩니다. 구독 폼 코드를 살펴보면 아래와 같은 형식의 주소를 발견하실 수 있습니다.

```
https://stibee.com/api/v1.0/lists/OOOOOOOOOOOOOOO/TYW5AcyOVE51JOZtmxyaTL8zPkJ/public/subscribers
```

&#x20;

이 주소 뒤에 ?groupIds={groupid} 값을 추가하면 됩니다. 예를 들어, 그룹의 아이디가 12345인 경우 아래와 같이 url을 수정하시면 됩니다.

* https://stibee.com/api/v1.0/lists/OOOOOOOOOOOOOOO/TYW5AcyOVE51JOZtmxyaTL8zPkJ/public/subscribers?groupIds=**12345**

\* _그룹 아이디(group id)를 확인하는 방법은 도움말 위쪽의 내용을 참고해 주세요._

\
페이지 URL 그룹 파라미터 사용하기

페이지 URL 뒤에 그룹 코드를 추가하면 구독자를 그룹으로 자동 분류할 수 있습니다.&#x20;

그룹을 만들고 관리하는 방법이 궁금하면 [주소록 그룹은 어떻게 사용하나요?](https://help.stibee.com/hc/ko/articles/4756567819791)를 참고하세요.

그룹이 아닌 사용자 정보를 입력하는 사용자 정의 필드 파라미터를 사용하고 싶은 경우 [페이지 URL 사용자 정의 필드 파라미터 사용하기](https://help.stibee.com/hc/ko/articles/4971235702287)를 참고하세요.

### &#x20;

### 페이지 URL 그룹 파라미터 사용하기

페이지 URL은 아래의 형식으로 생성됩니다.

* [https://{subdomain}.stibee.com/](https://page.stibee.com/subscriptions/%7Blistid%7D)
* 예. [https://syoletter.stibee.com/](https://page.stibee.com/subscriptions/3)

이 URL 뒤에 아래의 형식으로 "groupIds"(대소문자 구분)라는 파라미터를 추가하면 그룹을 지정할 수 있습니다. ("groupIds"의 "I"는 대문자 "I"(아이)입니다.)

* [https://{subdomain}.stibee.com/](https://page.stibee.com/subscriptions/%7Blistid%7D)**?groupIds={groupid}**
* 예: [https://syoletter.stibee.com/?groupIds=44737](https://page.stibee.com/subscriptions/3?groupIds=44737)

groupid(그룹에 할당된 고유의 아이디)는 아래 방법으로 확인할 수 있습니다.

* 주소록 목록에서 주소록 이름을 클릭하여 "주소록 대시보드"로 이동
* "그룹"을 클릭하여 그룹 목록으로 이동
* 그룹 이름을 클릭하여 그룹 필터링이 적용된 구독자 목록으로 이동
* 브라우저에 표시되는 URL에서 "subscribers/S" 뒤의 숫자를 확인

![](https://help.stibee.com/hc/article\_attachments/4756518765455/6270c2ccec5fb.png)

한 번에 여러개의 그룹에 추가하려면, 쉼표(,)로 구분하여 "groupIds" 파라미터를 여러 개 추가하면 됩니다. ("groupIds"의 "I"는 대문자 "I"(아이)입니다.)

* [https://{subdomain}.stibee.com/](https://page.stibee.com/subscriptions/%7Blistid%7D)**?groupIds={groupid},{groupid}**
* 예: [https://syoletter.stibee.com/?groupIds=44737,44738](https://page.stibee.com/subscriptions/3?groupIds=44737,44738)

이 기능을 사용하면, 제한적이지만, 구독 신청을 받을 때 직접 입력받지 않고도 추가적인 정보를 수집할 수 있습니다.

\
예를 들어, 구독자를 모으기 위해 페이지 URL을 여러 채널에 홍보를 한다고 가정해보겠습니다. 유입 경로별로 그룹을 만들고(예. "페이스북", "인스타그램", "블로그"), 동일한 페이지에 대해 각 그룹별 파라미터를 추가하여 사용하면, 유입 경로에 따라 각각 다른 그룹에 구독자를 추가할 수 있습니다.



## 구독 폼 URL 사용자 정의 필드 파라미터 사용하기

구독 폼 URL 뒤에 사용자 정의 필드 키 값을 파라미터로 추가하면 구독자 정보를 자동으로 추가할 수 있습니다.\
\
파라미터란, URL에 특정한 형식을 넣어 미리 값이 적용될 수 있도록 하는 기능을 의미합니다. 파라미터가 없는 경우에는 값이 빈 상태로 보여지며, 파라미터가 있다면 값이 미리 등록됩니다. (파라미터로 값이 미리 등록되어 있어도 값을 바꾸면 바꾼 값으로 저장됩니다.)

&#x20;

### 파라미터 이해하기 <a href="#h_d40a8d0a90" id="h_d40a8d0a90"></a>

구독 폼 URL에 이름 필드(name)를 파라미터로 미리 입력했을 때와 입력하지 않았을 때의 차이를 아래 URL을 통해서 확인할 수 있습니다.

\
**파라미터가 적용되지 않은 구독 폼 URL**

* [https://page.stibee.com/subscriptions/187957](https://page.stibee.com/subscriptions/187957)

![](https://downloads.intercomcdn.com/i/o/528905334/cf182df81c68614d8710df40/%EC%82%AC%EC%9A%A9%EC%9E%90%EC%A0%95%EC%9D%98%ED%95%84%EB%93%9C%ED%8C%8C%EB%9D%BC%EB%AF%B8%ED%84%B0\_1.png)

**파라미터가 적용된 구독 폼 URL**

* [https://page.stibee.com/subscriptions/187957**?name=스티비**](https://page.stibee.com/subscriptions/187957?name=%EC%8A%A4%ED%8B%B0%EB%B9%84)

![](https://downloads.intercomcdn.com/i/o/528906705/3316d4962d11a180cd50400c/%EC%82%AC%EC%9A%A9%EC%9E%90%EC%A0%95%EC%9D%98%ED%95%84%EB%93%9C%ED%8C%8C%EB%9D%BC%EB%AF%B8%ED%84%B0\_2.png)

스티비 구독 폼 뿐만 아니라 [페이지](https://help.stibee.com/hc/ko/articles/4971235702287)에서도 동일하게 파라미터를 추가해 사용할 수 있습니다. 구독 폼 URL 파라미터를 사용해 [추천인 기능](https://help.stibee.com/hc/ko/articles/4971631583119)을 구현할 수 있고 이외에도 다양한 정보를 수집할 수 있습니다.\
\
구독 시 그룹으로 자동 분류하고 싶다면 [그룹 파라미터](https://help.stibee.com/hc/ko/articles/4756482888463)를 사용하면 됩니다.

&#x20;

### 구독 폼 URL 사용자 정의 필드 파라미터 사용하기 <a href="#h_56b1e65f3d" id="h_56b1e65f3d"></a>

구독 폼 URL은 아래의 형식으로 생성됩니다.

* [https://page.stibee.com/subscriptions/{listid}](https://page.stibee.com/subscriptions/%7Blistid%7D)
* 예. [https://page.stibee.com/subscriptions/3](https://page.stibee.com/subscriptions/3)

이 URL 뒤에 아래의 형식으로 "사용자 정의 필드의 키 값"을 추가하면 구독 시 구독자 정보에 원하는 값이 자동으로 입력되도록 설정할 수 있습니다.

* [https://page.stibee.com/subscriptions/{listid}](https://page.stibee.com/subscriptions/%7Blistid%7D)**?field\_key={field\_value}**
* 예. [https://page.stibee.com/subscriptions/3?route=stibee](https://page.stibee.com/subscriptions/3?route=stibee)

field\_key는 사용자 정의 필드의 키 값으로 주소록 내 사용자 정의 필드에서 확인할 수 있습니다.

![](https://downloads.intercomcdn.com/i/o/525689679/c19b573c5f701291070f790d/%EC%82%AC%EC%9A%A9%EC%9E%90%EC%A0%95%EC%9D%98%ED%95%84%EB%93%9C%ED%8C%8C%EB%9D%BC%EB%AF%B8%ED%84%B0\_3.gif)

### 주의사항 <a href="#h_4e85a7ce6d" id="h_4e85a7ce6d"></a>

* 사용자 정의 필드에 없는 필드를 파라미터로 넣는 경우 정보가 입력되지 않습니다.
* 구독 폼에서 파라미터로 설정한 필드의 값을 구독자가 변경하는 경우 변경된 값으로 정보가 입력됩니다.

## 페이지 URL 사용자 정의 필드 파라미터 사용하기

페이지 URL 뒤에 사용자 정의 필드 키 값을 파라미터로 추가하면 구독자 정보를 자동으로 추가할 수 있습니다.\
\
파라미터란, URL에 특정한 형식을 넣어 미리 값이 적용될 수 있도록 하는 기능을 의미합니다. 파라미터가 없는 경우에는 값이 빈 상태로 보여지며, 파라미터가 있다면 값이 미리 등록됩니다. (파라미터로 값이 미리 등록되어 있어도 값을 바꾸면 바꾼 값으로 저장됩니다.)

&#x20;

### 파라미터 이해하기 <a href="#h_9840f80d07" id="h_9840f80d07"></a>

페이지 구독 폼 URL에 이름 필드(name)를 파라미터로 미리 입력했을 때와 입력하지 않았을 때의 차이를 아래 이미지를 통해서 확인할 수 있습니다.

&#x20;

**파라미터가 적용되지 않은 페이지 URL**

* https://{subdomain}.stibee.com (subdomain은 페이지 설정에 따라 달라집니다.)

![](https://downloads.intercomcdn.com/i/o/528915667/9985ee2c3099df298980205b/%ED%8E%98%EC%9D%B4%EC%A7%80%EC%82%AC%EC%9A%A9%EC%9E%90%EC%A0%95%EC%9D%98%ED%95%84%EB%93%9C%ED%8C%8C%EB%9D%BC%EB%AF%B8%ED%84%B0\_1.gif)&#x20;

**파라미터가 적용된 페이지 URL**

* https://{subdomain}.qa-page.stibee.com**?name=스티비** (subdomain은 페이지 설정에 따라 달라집니다.)

![](https://downloads.intercomcdn.com/i/o/528916728/c5df1c069d7c9bfffede6c13/%ED%8E%98%EC%9D%B4%EC%A7%80%EC%82%AC%EC%9A%A9%EC%9E%90%EC%A0%95%EC%9D%98%ED%95%84%EB%93%9C%ED%8C%8C%EB%9D%BC%EB%AF%B8%ED%84%B0\_2.gif)&#x20;

페이지가 아닌 일반 [구독 폼](https://help.stibee.com/hc/ko/articles/4971284625807)에서도 파라미터를 추가해 사용할 수 있습니다. 사용자 정의 필드 URL 파라미터를 사용해 [추천인 기능](https://help.stibee.com/hc/ko/articles/4971631583119)을 구현할 수 있고 이외에도 다양한 정보를 수집할 수 있습니다.\
\
페이지에서도 그룹으로 자동 배정이 되는 그룹 파라미터 기능을 사용할 수 있습니다.\
\
페이지에서 구독 시 그룹으로 자동 분류하고 싶다면 [그룹 파라미터](https://help.stibee.com/hc/ko/articles/4756482888463)를 페이지 URL 뒤에 넣어서 사용하면 됩니다.

&#x20;

### 페이지 URL 사용자 정의 필드 파라미터 사용하기 <a href="#h_b4c1c49ce3" id="h_b4c1c49ce3"></a>

페이지 URL은 아래의 형식으로 생성됩니다.

* [https://{subdomain}.stibee.com](https://{subdomain}.stibee.com/)
* 예. [https://syoletter.stibee.com](https://syoletter.stibee.com/subscribe/)

이 URL 뒤에 아래의 형식으로 "사용자 정의 필드의 키 값"을 추가하면 구독 시 구독자 정보에 원하는 값이 자동으로 입력되도록 설정할 수 있습니다.

* [https://{subdomain}.stibee.com](https://{subdomain}.stibee.com/)**?field\_key={field\_value}**
* 예. [https://syoletter.stibee.com?route=stibee](https://page.stibee.com/subscriptions/3?route=stibee)

field\_key는 사용자 정의 필드의 키 값으로 주소록 내 사용자 정의 필드에서 확인할 수 있습니다.

![](https://downloads.intercomcdn.com/i/o/528908888/5134a4728a731241b7fd2c2b/%EC%82%AC%EC%9A%A9%EC%9E%90%EC%A0%95%EC%9D%98%ED%95%84%EB%93%9C%ED%8C%8C%EB%9D%BC%EB%AF%B8%ED%84%B0\_3.gif)&#x20;

#### **주의사항** <a href="#h_e7965db396" id="h_e7965db396"></a>

* 사용자 정의 필드에 없는 필드를 파라미터로 넣는 경우 정보가 입력되지 않습니다.
* 페이지의 구독 폼에서 파라미터로 설정한 필드의 값을 구독자가 변경하는 경우 변경된 값으로 정보가 입력됩니다.

\
내용 중 ‘페이지’로 신청 받는 경우에도 자동 분류할 수 있음을 안내하고 여기 링크에서 확인하도록 유도

