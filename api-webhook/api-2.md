# 자동 이메일 API

**💬** 이 내용은 **스탠다드, 프로, 엔터프라이즈** 요금제에 해당하는 도움말입니다.

&#x20;

### 이 글에서는 <a href="#id-01h8n94xsyb5amd8e84wg74fkq" id="id-01h8n94xsyb5amd8e84wg74fkq"></a>

자동 이메일 API를 요청하는 방법에 대한 기술적인 설명을 담고 있습니다.&#x20;



## 자동 이메일 API 이해하기

자동 이메일의 트리거 중 \[API로 직접 요청]을 사용하면 API로 자동 이메일 발송을 요청하는 것이 가능합니다. 내부적으로 개발이 가능하다면 이 기능을 사용해 자동 이메일을 다양한 시나리오로 구현할 수 있습니다. 예를 들어 '장바구니에 물건을 담아두고 N일이 경과했지만 구매 하지 않은 고객'에게 구매를 유도하기 위해 자동으로 할인 쿠폰 정보를 담은 이메일을 보내는 것도 가능합니다. 자동 이메일 API를 사용하는 방법을 알아봅니다.

자동 이메일을 API로 요청해서 발송한다는 것은, 스티비가 제공하는 API 엔드포인트로 POST 메소드로 요청하여, 미리 설정한 이메일을 발송한다는 의미입니다. 자동 이메일 API를 사용하면 다양한 종류의 시스템 성 이메일(예: 인증 메일, 결제 안내 등 사용자 행동에 따른 시스템 성 이메일)을 자동으로 구현할 수 있습니다.\
\
_**\***_**주의!**_'_자동 이메일 API'는 개별 이메일 발송에 최적화되어 있으며 '대량 발송'에는 적합하지 않습니다. 대량 발송의 경우에는 [일반 이메일](https://help.stibee.com/hc/ko/articles/4872426850703) 기능을 사용해 발송하는 것을 권장합니다.\
\


## 자동 이메일 API 사용하기

### API 키 만들기 <a href="#id-1-api" id="id-1-api"></a>

자동 이메일 API를 사용하려면 우선 스티비에서 API 키를 만들어야 합니다. API는 계정 단위로 관리되기 때문에 API 키의 생성과 관리는 모두 사용자 메뉴의 **계정** **API 키**에서 이루어집니다.

&#x20;

<figure><img src="https://help.stibee.com/hc/article_attachments/4756529650831" alt=""><figcaption></figcaption></figure>

### API 사용하기 <a href="#id-2-api" id="id-2-api"></a>

**계정** **API 키**에서 API 키를 생성한 뒤, API 키 옆의 **복사하기**를 클릭하면 API 키를 복사할 수 있습니다. 이 키는 API 요청 시 토큰으로 사용됩니다. API 키가 노출되면 스티비 계정 보안에 치명적인 문제가 생길 수 있으니 주의하세요. 만약 노출이 의심되면 **계정** **API 키**에서 해당 키를 비활성화하거나 삭제하고 새로운 키를 만드세요.

<figure><img src="https://help.stibee.com/hc/article_attachments/4756529663759" alt=""><figcaption></figcaption></figure>

&#x20;

### 자동 이메일 API 엔드포인트 확인하기 <a href="#id-3-api" id="id-3-api"></a>

자동 이메일 발송 조건의 트리거를 "API로 요청하기"로 설정하면 자동 이메일 API의 Endpoint URL을 확인할 수 있습니다.

&#x20;

<figure><img src="https://help.stibee.com/hc/article_attachments/4756496083215" alt=""><figcaption></figcaption></figure>

이 URL은 자동 이메일 대시보드에서도 확인할 수 있습니다.

<figure><img src="https://help.stibee.com/hc/article_attachments/4756538295055" alt=""><figcaption></figcaption></figure>

&#x20;

### 자동 이메일 API 요청 및 응답 모델 <a href="#id-4-api" id="id-4-api"></a>

자동 이메일 API 요청 및 응답은 JSON 형식을 따릅니다. 예를 들어, 자동 이메일의 API 트리거를 실행하려면 POST Method로 다음과 같은 JSON 형식의 요청을 보냅니다.

_\* 자동 이메일 API는 1초당 10회, 1회당 256KB으로 제한되어 있습니다._\
**HTTP Methods**

* POST

**Endpoint URL**

* [https://stibee.com/api/v1.0/auto/](https://stibee.com/api/v1.0/auto/)...

**Header**

* AccessToken: API 키
* Content-Type: application/json

**Request Body**

* subscriber: 자동 발송할 대상이 되는 구독자의 이메일 주소입니다.

&#x20;

### 자동 이메일 API 요청 및 응답 예제 <a href="#id-5-api" id="id-5-api"></a>

"[user@domain.com](mailto:user@domain.com)"로 자동 이메일 발송을 할 경우, 다음과 같이 요청합니다.

```json
POST https://stibee.com/api/v1.0/auto/...
{
    "subscriber": "user@domain.com"
}
```

&#x20;

이에 대한 응답은 다음과 같습니다.

```json
200 OK
```

이 응답 값이 이메일 발송 성공, 실패를 의미하는 것은 아닙니다. 200 OK 응답이 왔더라도 이메일 발송은 실패할 수 있습니다. 이메일 발송 성공, 실패 결과는 이메일의 상세 통계 화면에서 확인할 수 있습니다. 이메일 발송 실패에 대한 자세한 내용은 [발송을 완료했는데 이메일이 도착하지 않습니다](https://help.stibee.com/hc/ko/articles/4756538892943)를 참고하세요.

응답 결과와 상관없이 "[user@domain.com](mailto:user@domain.com)"이 자동 이메일의 주소록에 포함되어있지 않거나 수신거부, 자동삭제된 구독자라면, 트리거가 실행되지 않습니다.

&#x20;

### 자동 이메일 API에서 사용자 정의 필드 사용하기 <a href="#id-6-api" id="id-6-api"></a>

자동 이메일 API로 이메일 발송을 요청할 때, 이메일 주소 외에도 다른 값을 전송할 수 있습니다. 주소록 - '[사용자 정의 필드](https://help.stibee.com/hc/ko/articles/5659525285007-%EA%B5%AC%EB%8F%85%EC%9E%90-%EC%A0%95%EB%B3%B4-%EC%84%A4%EC%A0%95%ED%95%98%EA%B8%B0-%EC%82%AC%EC%9A%A9%EC%9E%90-%EC%A0%95%EC%9D%98-%ED%95%84%EB%93%9C)'에서 사용하려는 필드를 미리 추가한 후 아래 방법으로 API를 요청하면 됩니다.\
\
이렇게 하면 자동 이메일에서도 제목에 구독자 이름을 넣거나, 본문에 고객마다 다른 값(예. 적립금, 구매한 상품 이름 등)을 표시할 수 있습니다.\
\
자동 이메일 API에서 이메일 주소 외 다른 값을 넣어 요청하는 방법은 다음과 같습니다.

```json
POST https://stibee.com/api/v1.0/auto/...
{
    "subscriber": "user@domain.com"
    "key1": "value1",
    "key2": "value2",
    ...
}
```

이메일 제목이나 미리보기 텍스트, 이메일 본문에서 "$%key1%$", "$%key2%$"의 형식으로 사용자 정의 필드를 입력하면, 이메일이 발송될 때 key1, key2에 해당하는 값으로 치환되어 발송됩니다.

&#x20;

#### 사용자 정의 필드 값 내 HTML 코드 사용 <a href="#html" id="html"></a>

이메일 본문이 HTML로 구성되기 때문에 치환하는 값 안에 \<br>태그 외의 다른 HTML 태그를 사용하는 것도 가능하지만, 이렇게 사용된 태그에 대해 스티비에서 호환성을 보장하지는 않습니다. 예를 들어, 태그가 이메일 수신 환경에서 동작하지 않거나, 특정 태그로 인해 레이아웃이 깨질 수도 있습니다.\
\
치환하는 값 안에서 줄바꿈을 하려면 HTML 태그 중 \<br> 태그를 사용하면 됩니다. 예를 들어 자동 이메일 API 요청을 다음과 같이 했다고 가정해보겠습니다.

```json
POST https://stibee.com/api/v1.0/auto/...
{
    "subscriber": "user@domain.com"
    "key1": "안녕하세요!<br>스티비 팀입니다.",
    ...
}
```

이메일 본문에 "$%key1%$"라는 텍스트가 포함되어있다면 이메일이 발송될 때 이렇게 치환되어 발송됩니다.

&#x20;

**발송하기 전 이메일 본문 원본(치환 전)**

```json
...
$%key1%$
...
```

&#x20;

**발송된 이메일 본문(치환 후)**

```json
...
안녕하세요!
스티비 팀입니다.
...
```

&#x20;

#### 주소록의 사용자 정의 필드와의 관계 <a href="#undefined" id="undefined"></a>

자동 이메일 API에서 사용되는 사용자 정의 필드는, 주소록의 사용자 정의 필드와 서로 영향을 주지 않으며, 더 높은 우선순위를 갖습니다.\
\
예를 들어, 주소록에 "[gildong@stibee.com](mailto:gildong@stibee.com)"라는 구독자가 있고, 이 구독자의 "name"이라는 사용자 정의 필드의 값이 "길동"이라고 가정해보겠습니다. 이 구독자에게 자동 이메일 API로 "name"이라는 사용자 정의 필드에 "둘리"라는 값을 넣어 발송 요청을 하면 어떻게 될까요?

* 주소록의 사용자 정의 필드 값인 "길동"보다 자동 이메일 API의 사용자 정의 필드 값인 "둘리"가 더 높은 우선순위를 갖습니다. **따라서, 발송되는 이메일에는 "둘리"라는 값이 표시됩니다.**
* 주소록의 사용자 정의 필드와 자동 이메일 API는 서로 영향을 주지 않기 때문에, **주소록의 "name"이라는 사용자 정의 필드의 값은 변경되지 않고 "길동"으로 유지됩니다.**

일반 이메일에서 사용자 정의 필드를 사용하는 방법은 [이메일 제목에 구독자 이름을 넣을 수 있나요?](https://help.stibee.com/hc/ko/articles/4756474635407)를 참고하세요.

\
