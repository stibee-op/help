# 페이지 URL 그룹 파라미터 사용하기

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
