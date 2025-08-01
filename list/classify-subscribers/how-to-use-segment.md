# 세그먼트 사용하기

## 이 글에서는 <a href="#h_01h984hy14dfxnh2ehhdyp0nyq" id="h_01h984hy14dfxnh2ehhdyp0nyq"></a>

구독자를 자동으로 분류할 수 있는 세그먼트 기능에 대해서 알아봅니다. 세그먼트 기능을 사용하면 원하는 구독자 정보 조건에 따라 쉽게 구독자를 분류하고 이메일을 발송할 수 있습니다.

***

세그먼트를 이용할 경우, 원하는 조건만 설정하면 각 조건에 맞는 구독자가 자동으로 분류됩니다. \[[그룹](how-to-use-groups.md)] 기능과 달리 분류되는 구독자가 설정한 조건에 따라 동적으로 할당되는 특성을 가집니다.



## **세그먼트 만들기** <a href="#h_01gsyq9tkwga8ptn993qfd94n9" id="h_01gsyq9tkwga8ptn993qfd94n9"></a>

{% hint style="info" %}
세그먼트 목록에 표시되는 숫자는 10분 간격으로 자동 업데이트 됩니다. 구독자 수가 변경되지 않는다면 조건을 잘 설정했는지 먼저 확인해 주시고, 설정에 이상이 없다면 잠시 기다려 주세요
{% endhint %}

1. 세그먼트를 만들고 싶은 \[주소록]을 선택하고, \[세그먼트]를 클릭합니다.
2. 세그먼트 목록 화면에서 \[+새로 만들기]를 클릭합니다.
3. 세그먼트의 설정 창이 나타나면 세그먼트 이름을 입력하고, 세그먼트를 구성할 조건을 추가합니다.

세그먼트는 생성 순서 기준으로 자동 정렬됩니다. 이메일을 발송할 때 주소록의 세그먼트를 선택하여(복수 선택 가능) 발송할 수 있습니다.

만들 수 있는 세그먼트의 수는 사용하고 있는 요금제에 따라 달라집니다.

* 스타터 요금제: 주소록 당 1개의 세그먼트를 만들 수 있습니다.&#x20;
* 스탠다드 요금제: 주소록 당 5개의 세그먼트를 만들 수 있습니다.&#x20;
* 프로 요금제 : 주소록 당 10개의 세그먼트를 만들 수 있습니다.
* 엔터프라이즈 요금제 : 세그먼트 개수에 제한이 없습니다.&#x20;

![](<../../.gitbook/assets/2 (8).png>)



## **세그먼트 설정하기** <a href="#h_01gsyqak6a24rakfc5qcweyc2m" id="h_01gsyqak6a24rakfc5qcweyc2m"></a>

### 세그먼트 생성 기준 <a href="#h_01h6dw8tez94hm2d14m73w0c2x" id="h_01h6dw8tez94hm2d14m73w0c2x"></a>

세그먼트는 여러 조건으로 구성됩니다. 각 조건은 '구독자 정보 또는 구독자 활동 + 판단 값 + 기준' 세 가지 요소로 구성됩니다.

예를 들어, '거주지'에 '서울'이 '포함되는' 구독자를 세그먼트로 분류하고 싶다면, 아래처럼 조건을 설정하면 됩니다.

* 조건: 거주지 + 서울 + 포함됨

조건은 한 번에 하나만 설정할 수도 있고, AND 또는 OR로 여러 조건을 동시에 설정할 수도 있습니다.

<figure><img src="../../.gitbook/assets/3 (9).png" alt=""><figcaption></figcaption></figure>



### **구독자 정보와 구독자 활동 이해하기** <a href="#information-activity" id="information-activity"></a>

세그먼트의 조건을 구성할 요소로 '구독자 정보' 또는 '구독자 활동'을 선택할 수 있습니다. _구독자 활동 세그먼트는 프로 요금제부터 제공하는 기능입니다._

* 구독자 정보: 연령대, 성별과 같이 \[주소록 → [사용자 정의 필드](../adding-managing-subscriber/understanding-subscriber-info.md#h_01gw45zrwcjd1eg1cam4vhw25m)]에서 미리 정의되고 수집한 정보입니다. 구독자 정보에 새로운 항목을 추가하고 싶다면, \[사용자 정의 필드]에서 \[+필드 추가하기]를 사용해 주세요.&#x20;
* 구독자 활동: 오픈이나 클릭과 같이 이메일을 받아본 구독자의 활동 정보를 의미합니다. 예를 들어 dooly@stibee.com 구독자가 이메일을 오픈했거나 이메일에 있는 링크를 클릭한 경우 등을 의미합니다. 구독자 활동 정보는 임의로 추가할 수 없습니다.

{% hint style="info" %}
구독자 활동 세그먼트의 '최근 n개', '최근 n일' 조건은 발송 완료된 \[일반 이메일]을 기준으로 구독자를 분류합니다. \[자동 이메일]은 분류 조건에 포함되지 않는 점 참고해 주세요.
{% endhint %}

![](<../../.gitbook/assets/4 (8).png>)



### **구독자 정보와 구독자 활동 분류 기준**

구독자 정보 또는 구독자 활동 중 어느 요소를 선택하는지에 따라 설정할 수 있는 기준의 종류가 달라집니다.&#x20;

#### **구독자 정보를 분류하는 기준**

* 포함됨: 조건 입력창의 텍스트가 구독자 정보에 포함되어 있습니다.&#x20;
* 포함되지 않음: 조건 입력창의 텍스트가 구독자 정보에 포함되어 있지 않습니다.
* 같음: 조건 입력창의 텍스트가 구독자 정보와 완전히 일치합니다.
* 같지 않음: 조건 입력창의 텍스트가 구독자 정보와 완전히 일치하지 않습니다.
* 시작함: 구독자 정보가 조건 입력창의 텍스트로 시작합니다.
* 끝남: 구독자 정보가 조건 입력창의 텍스트로 끝납니다.&#x20;
* 비어있음: 구독자 정보에 입력값이 없습니다.
* 비어있지 않음: 구독자 정보에 입력값이 있습니다.&#x20;

#### **\[포함됨]과 \[같음]의 동작 방식 차이**

'포함됨'과 '같음'은 동작하는 방식이 다릅니다. 예를 들어 세그먼트의 조건으로 구독자 정보를 '지역'으로 설정하고 가운데의 판단 값을 '서울'로 설정했다고 가정하겠습니다.&#x20;

만약에 조건을 \[**포함됨**]으로 설정했다면,

* 저장된 구독자의 지역 정보가 '서울특별시'라면 텍스트의 일부에 판단 값인 '서울'이 포함되어 있습니다.
* 따라서 이 구독자는 조건을 만족한다고 판단합니다.&#x20;

만약에 조건을 \[**같음**]으로 설정했다면,

* 저장된 구독자의 지역 정보가 '서울특별시'라면 판단 값인 '서울'과 정확히 같지 않습니다.
* 따라서 이 구독자는 조건을 만족하지 않는다고 판단합니다.&#x20;

#### **구독자 활동을 분류하는 기준**&#x20;

* 발송 성공/실패: 발송 여부로 구독자를 분류합니다. &#x20;
* 오픈/오픈 안 함: 오픈 여부로 구독자를 분류합니다.&#x20;
* 클릭/클릭 안 함: 클릭 여부로 구독자를 분류합니다.



## **조건 설정 예시** <a href="#h_01gsyvcz3ephdtxjws2rx90xeq" id="h_01gsyvcz3ephdtxjws2rx90xeq"></a>

{% hint style="info" %}
예시에서 사용하는 \[연령대] 필드는 설명을 위해 임의로 설정한 필드입니다. 기본적으로 제공하는 정보가 아니므로 '연령대'라는 정보를 활용하고 싶은 경우에는 직접 사용자 정의 필드에 관련 항목을 추가하고, 구독자 정보를 수집해서 주소록에 입력해야 합니다.&#x20;
{% endhint %}

**예시1.**

구독자 중 연령대가 20대인 사람만 분류하고 싶다면,

1. 조건의 첫 번째 칸 \[구독자 정보]를 '연령대'로 선택합니다.&#x20;
2. 가운데 텍스트 입력 칸에 '20대'를 판단 값으로 입력합니다.
3. 조건의 마지막, 기준을 \[같음]으로 선택합니다.

![](<../../.gitbook/assets/5 (6).png>)

**예시2.**

만약에 구독자 중 '연령대'가 20대 **이면서(AND)** '유입 채널'이 구글 검색인 사람을 분류하고 싶다면,&#x20;

1. 조건의 첫 번째 빈칸 \[구독자 정보]를 '연령대'로 선택합니다.
2. 조건의 가운데 텍스트 입력 칸에 '20대'를 입력합니다.
3. 조건의 마지막, 기준을 \[같음]으로 선택합니다.
4. \[+조건 추가]를 클릭합니다.
5. 새롭게 추가된 조건의 \[구독자 정보]를 '유입 채널'로 선택합니다.
6. 새로운 조건의 가운데 텍스트 입력 칸에 '구글 검색'을 입력합니다.&#x20;
7. 새로운 조건 마지막, 기준을 \[같음]으로 선택합니다.&#x20;
8. 조건 그룹 상단에 있는, '개별 조건이 모두 일치하는(AND)'를 선택합니다.&#x20;

\
'개별 조건 중 하나라도 **만족하는(OR)**'을 선택할 경우에는,

* 연령대가 '20대'이거나(OR),
* 채널이 '구글 검색'인 경우

둘 중 하나라도 포함되면 조건을 만족한 것으로 판단합니다.&#x20;

![](<../../.gitbook/assets/6 (6).png>)



## **세그먼트 관리하기** <a href="#h_01gsyvdptbbs67c27tkgxmjtt4" id="h_01gsyvdptbbs67c27tkgxmjtt4"></a>

### 세그먼트 정보 <a href="#h_01gsyq9h6yf7j8tf59cxyqmcpn" id="h_01gsyq9h6yf7j8tf59cxyqmcpn"></a>

생성한 세그먼트의 이름, 구독자 정보, 만든 날짜가 표시됩니다. 세그먼트 이름을 클릭하면 각 세그먼트의 설정에 따라 분류된 구독자 명단을 확인할 수 있습니다. _세그먼트 구분색은 자동으로 설정되며, 색상을 수정하는 것은 불가능합니다._

<figure><img src="../../.gitbook/assets/7 (5).png" alt=""><figcaption></figcaption></figure>

### 세그먼트 수정, 복사, 삭제하기 <a href="#h_01gsyq9p3q52y092n4a23pcxjc" id="h_01gsyq9p3q52y092n4a23pcxjc"></a>

생성한 세그먼트를 수정하거나 복사, 삭제할 수 있습니다.

* **수정:** 이미 만든 세그먼트의 이름을 수정하거나 설정한 조건을 수정할 수 있습니다.
* **복사:** 세그먼트를 복사할 수 있습니다. 클릭하면 바로 동일한 조건과 이름이 설정된 '사본' 세그먼트가 생성됩니다.
* **삭제:** 생성한 세그먼트를 삭제합니다.&#x20;

{% hint style="info" %}
세그먼트를 삭제해도 구독자 정보는 삭제되지 않습니다. 삭제한 세그먼트는 복구할 수 없습니다.&#x20;
{% endhint %}

<figure><img src="../../.gitbook/assets/8 (7).png" alt=""><figcaption></figcaption></figure>

### **세그먼트로 이메일 발송하기** <a href="#h_01gsyqasmq0tv4x3m6abapy1zz" id="h_01gsyqasmq0tv4x3m6abapy1zz"></a>

이메일 편집 단계 중 \[주소록] 단계에서, 이메일을 보내고 싶은 세그먼트를 선택해서 발송하면 됩니다.&#x20;

1. 이메일 편집을 시작합니다.
2. 이메일 편집 단계 중, 첫 단계인 \[주소록] 단계로 이동합니다.
3. 세그먼트를 선택한 주소록을 선택하고 \[세그먼트, 그룹] 메뉴를 클릭해서 발송을 원하는 세그먼트를 선택합니다.
4. 이메일을 발송합니다.

![](<../../.gitbook/assets/9 (8).png>)



\[사용자 정의 필드] 파라미터를 사용하면 특정 구독 폼 URL을 통해 유입되는 구독자는 자동으로 사용자 정의 필드에 특정 값이 입력되도록 설정할 수 있습니다. 이 기능을 활용해서 새로 추가된 구독자를 특정 세그먼트로 자동 분류할 수도 있어요. 자세한 내용은 [how-to-use-custom-field-parameter.md](../../page/subscribe/how-to-use-custom-field-parameter.md "mention") 도움말을 참고해 주세요.
