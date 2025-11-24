# 구독자를 자동으로 분류하기

### 이 글에서는

페이지 URL 뒤에 그룹 id, 사용자 정의 필드 키(key)를 추가하면 구독자를 자동으로 분류할 수 있습니다. 이 방법에 관해 알아봅니다.

***

## 파라미터 이해하기 <a href="#parameter" id="parameter"></a>

파라미터는 URL 뒤에 특정 값을 추가해 구독 폼의 입력값을 미리 채워두는 기능입니다. 파라미터가 없으면 값이 빈 상태로 보이며, 파라미터가 있다면 값이 미리 등록됩니다. 구독자는 자동 입력된 값을 그대로 제출할 수도 있고, 수정해 다른 값을 입력할 수도 있습니다.

예를 들어, 페이지 URL에 이름(name) 필드를 파라미터로 미리 입력했을 때와 입력하지 않았을 때를 비교해 보면,

* 파라미터가 적용되지 않은 페이지 URL에서 \[구독하기]를 눌렀을 때: https://helpstibee.stibee.com
  * 이름 필드가 비어 있습니다.

<figure><img src="../../.gitbook/assets/페이지 파라미터.png" alt=""><figcaption></figcaption></figure>



* 파라미터가 적용된 페이지 URL에서 \[구독하기]를 눌렀을 때: https://helpstibee.stibee.com?name=스티비
  * 이름 필드에 '스티비'가 자동 입력됩니다.

<figure><img src="../../.gitbook/assets/페이지 파라미터2.png" alt=""><figcaption></figcaption></figure>



## 그룹으로 자동 분류하기 <a href="#parameter-group" id="parameter-group"></a>

구독자를 모집할 때, 구독자가 직접 입력하지 않은 정보도 파라미터로 분류할 수 있습니다.

예를 들어, 페이지 링크를 여러 SNS에 홍보하는 경우, URL마다 다른 그룹 파라미터를 넣어 유입 경로별 그룹 분류가 가능합니다.

* https://helpstibee.stibee.com/?groupIds=44737 (페이스북 그룹)
* https://helpstibee.stibee.com/?groupIds=43677 (인스타그램 그룹)

#### 사용 방법

페이지 URL 형식은 다음과 같습니다.

* https://{subdomain}.stibee.com

특정 그룹에 구독자를 자동 분류하는 페이지 URL 형식은 다음과 같습니다.

* https://{subdomain}.stibee.com/?groupIds={groupid}

한 번에 여러 개의 그룹에 분류하려면 그룹 파라미터를 여러 개 추가한 뒤, 쉼표로 구분하면 됩니다.

* https://{subdomain}.stibee.com/?groupIds={groupid},{groupid}

#### 그룹 ID 확인 방법

1. 주소록 목록에서 원하는 주소록 선택
2. \[그룹] 메뉴로 이동
3. 그룹 이름 클릭
4. 브라우저 URL의 subscribers/S 뒤 숫자 확인

{% hint style="info" %}
그룹이 삭제되더라도 기존 URL은 계속 사용할 수 있지만, 그룹 자동 분류는 적용되지 않습니다.

그룹과 관련한 자세한 내용은 [그룹 사용하기](../../list/classify-subscribers/how-to-use-groups.md) 도움말을 참고해 주세요.
{% endhint %}



예를 들어, 그룹 ID가 44737이라면 URL은 다음과 같습니다.

* 일반 페이지 URL: https://newsletter.stibee.com
* 418191 그룹에 구독자를 추가하는 페이지 URL: https://helpstibee.stibee.com/?groupIds=418191
* 418191, 418190 그룹에 구독자를 추가하는 페이지 URL: https://helpstibee.stibee.com/?groupIds=418191,418190

<figure><img src="../../.gitbook/assets/페이지 파라미터3.png" alt=""><figcaption></figcaption></figure>



## 구독자 정보에 자동으로 특정 값 입력하기

구독자를 모집할 때, 구독자가 직접 입력하지 않은 정보도 파라미터로 자동 수집할 수 있습니다.

사용자 정의 필드의 키(key)를 파라미터로 넣으면, 구독자가 구독을 신청할 때 해당 값이 자동으로 입력됩니다.

#### 사용 방법

**\*주의:** field\_key의 I는 영어 대문자 I(아이)입니다.

페이지 URL 형식은 다음과 같습니다.

* https://{subdomain}.stibee.com

특정 그룹에 구독자를 자동 분류하는 URL 형식은 다음과 같습니다.

* https://newsletter.stibee.com/?field\_key=field\_value

#### field\_key 확인 방법

field\_key는 \[주소록 → 사용자 정의 필드]의 '키' 값에서 확인할 수 있습니다.

1. 주소록 목록에서 원하는 주소록 선택
2. \[사용자 정의 필드] 메뉴로 이동   \
   &#xNAN;_\* 필요하다면 이 단계에서 \[사용자 정의 필드]를 새로 생성할 수 있습니다._
3. 키(key) 확인

{% hint style="info" %}
사용자 정의 필드가 삭제되더라도 기존 URL은 계속 사용할 수 있지만, 사용자 정의 필드 자동 입력은 적용되지 않습니다.

사용자 정의 필드 관련한 자세한 내용은 [구독자 정보 이해하기](../../list/adding-managing-subscriber/understanding-subscriber-info.md) 도움말을 참고해 주세요
{% endhint %}



예를 들어, 사용자 정의 필드 '유입 경로'의 키(key)가 route이고, 값에 stibee를 자동 입력하고 싶다면

* 일반 페이지 URL: https://newsletter.stibee.com
* '유입 경로' \[사용자 정의 필드]에 stibee 값을 자동 입력하는 페이지 URL: https://newsletter.stibee.com/?route=stibee



## 주의사항

* 사용자 정의 필드에 없는 필드를 파라미터로 넣는 경우 정보가 입력되지 않습니다.
* 페이지의 구독 폼에서 파라미터로 설정한 필드의 값을 구독자가 변경하는 경우 변경된 값으로 정보가 입력됩니다.
