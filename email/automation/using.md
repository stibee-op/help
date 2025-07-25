# 자동 이메일 사용하기

💬 이 내용은 **스탠다드, 프로, 엔터프라이즈 요금제**에 해당하는 도움말입니다.

## 이 글에서는 <a href="#h_01h9mnkve0157zzmzkm7q4xb50" id="h_01h9mnkve0157zzmzkm7q4xb50"></a>

스티비의 자동 이메일 기능을 사용하는 구체적인 방법에 대해 알아봅니다.

***

## 자동 이메일 발송 구조 이해하기

\[자동 이메일]은 구독자 한 명, 한 명에게 정확히 보내는 구조에 최적화되어 있습니다. 따라서, 자동 이메일을 한 번에 여러 명의 구독자에게 보내는 경우, [일반 이메일](broken-reference)과 처리 방식이 달라 발송 완료까지 시간이 오래 걸릴 수 있습니다. 스티비의 자동 이메일 기능을 사용하는 구체적인 방법에 대해 알아봅니다.

_\* 비밀번호 재설정 이메일, 웰컴 이메일과 같이 구독자별로 한 명, 한 명 발송하는 것이 아니라 한 번에 여러 명에게 동시에 보내는 이메일(예: 뉴스레터, 프로모션 메일 대량 발송하는 이메일)이라면 일반 이메일을 사용해서 보내주세요._



## 자동 이메일의 동작 방식 <a href="#h_01gh88jd5svt98k9ww8swjzm83" id="h_01gh88jd5svt98k9ww8swjzm83"></a>

자동 이메일의 상태는 '작성 중, 실행 중, 예약 중, 일시정지, 종료' 5가지로 구분할 수 있습니다.

자동 이메일은 \[[트리거](https://help.stibee.com/email/automation/using#trigger)]로 설정한 조건을 만족할 때마다 자동으로 설정해둔 이메일이 발송되는 방식입니다. 트리거는 자동 이메일이 '실행 중'인 경우에만 동작합니다.

{% hint style="info" %}
자동 이메일은 '실행중' 상태에서만 동작합니다. '작성중, 예약중, 일시정지, 종료' 상태인 경우 트리거가 동작하지 않기 때문에 트리거에 만족하는 동작이 발생해도 자동 이메일은 발송되지 않습니다.
{% endhint %}

<figure><img src="../../.gitbook/assets/image (69).png" alt=""><figcaption></figcaption></figure>



## 자동 이메일 만들기 <a href="#h_01gh88jk5dx5h8b3jvzzsxnaxr" id="h_01gh88jk5dx5h8b3jvzzsxnaxr"></a>

자동 이메일은 \[일반 이메일]과 마찬가지로 이메일 목록에서 만들 수 있습니다.

1. 화면 가장 위에 있는 메뉴에서 \[이메일]을 클릭하여 이메일 목록으로 이동합니다.
2. 이메일 목록 오른쪽 위에 있는 \[+ 새로 만들기 → 자동 이메일]을 클릭합니다.
3. \[자동 이메일]이 만들어지고 이메일이 발송될 \[[주소록](broken-reference)]을 선택하는 단계로 이동합니다.

<figure><img src="../../.gitbook/assets/자동 이메일_1.png" alt=""><figcaption></figcaption></figure>

### 주소록 설정하기 <a href="#h_01gh88jyrrk5z0rz9nejbjs7z3" id="h_01gh88jyrrk5z0rz9nejbjs7z3"></a>

자동 이메일도 일반 이메일과 마찬가지로 주소록을 선택해야 합니다.

한 가지 차이점은 \[일반 이메일]은 선택된 주소록에 등록된 전체 구독자에게 일괄 발송되지만, \[자동 이메일]은 선택된 주소록에 등록된 구독자 중 발송 조건에 따라 '각기 다른 사람'에게, '각기 다른 시점'에 발송됩니다. 자동 이메일에서 선택한 \[주소록]은 발송 조건에 따라 자동 이메일이 발송될 수 있는 일종의 '발송 대상 후보'입니다.

<figure><img src="../../.gitbook/assets/image (2) (1) (1).png" alt=""><figcaption></figcaption></figure>

### 발송 조건 설정하기 <a href="#h_01gh88k6hgnwr58y1m4k91qyvs" id="h_01gh88k6hgnwr58y1m4k91qyvs"></a>

자동 이메일이 일반 이메일과 다른 점은 \[발송 조건]을 설정한다는 것입니다. 발송 조건은 자동 이메일을 발송하기 위한 조건으로 '트리거, 필터, 발송 시간대, 반복 발송 설정'으로 구분합니다.

<figure><img src="../../.gitbook/assets/image (3) (1).png" alt=""><figcaption></figcaption></figure>

### **트리거** <a href="#trigger" id="trigger"></a>

트리거는 이메일을 발송할 기본 조건입니다. 이메일, 주소록에 대한 구독자의 행동이나 API 요청으로 실행됩니다. 트리거로 설정할 수 있는 구독자의 행동은 다음과 같습니다.

<figure><img src="../../.gitbook/assets/트리거 도움말 업데이트.png" alt=""><figcaption></figcaption></figure>

#### **구독자 정보 기반 트리거**

* **구독자 추가**
  * 주소록에 구독자가 추가됐을 때 자동 이메일을 발송합니다. '관리자가 직접 추가한 경우'를 포함하면, 구독 폼이 아니라 관리자가 직접 추가한 구독자에게도 자동 이메일을 보낼 수 있습니다.
    * 활용 예시: 뉴스레터를 새로 구독한 구독자에게 웰컴 이메일을 보내거나, 뉴스레터를 새로 구독한 사람에게 기존에 발송했던 뉴스레터를 다시 볼 수 있는 링크를 제공하는 이메일을 보냅니다.
* **구독자의 기념일**
  * 구독자의 '날짜' 형식 필드에 입력한 값을 기준으로 이메일을 발송합니다. 특정 날짜로부터 1일 전, 30일 전 등 기간을 설정해 자동으로 이메일을 보낼 수 있습니다.
    * 활용 예시: 구독자의 생일마다 자동으로 생일 축하 이메일을 보내거나, 구독자의 서비스 가입일을 기념하는 이메일을 보냅니다.
* **구독자 정보 업데이트(프로)**
  * 구독자의 사용자 정의 필드가 '특정 값'으로 업데이트 되면 자동 이메일을 발송합니다.
    * 활용 예시: 구독자의 등급이 'VIP' 회원으로 업데이트 되면 VIP 등급 혜택 안내 이메일을 보냅니다.
* **구독자 그룹 추가(프로)**
  *   '특정 그룹'에 구독자가 추가됐을 때 자동 이메일을 발송합니다.

      **\*주의:** 이미 주소록에 추가된 구독자가 주소록의 '특정 그룹'에 추가됐을 때만 동작합니다. 주소록에 존재하지 않는 구독자가 특정 그룹에 새로 추가됐을 때 자동 이메일을 보내고 싶다면 \[구독자 추가] 트리거를 활용하세요.

      * 활용 예시: 구독자가 '리마인드' 그룹에 추가되면, 리마인드 이메일을 보냅니다.

#### **구독자 활동 기반 트리거**

* **발송 성공**
  * 특정 이메일 발송을 성공한 구독자에게 자동 이메일을 보냅니다. 어떤 이메일에 관한 발송 성공인지 선택할 수 있으며, 이미 발송 완료된 일반 이메일이나 종료된 자동 이메일은 선택할 수 없습니다.
    * 활용 예시: 신규 회원에게 서비스 가이드를 2회에 걸쳐 제공하기 위해, 첫 번째 이메일이 발송 성공한 뒤, 이어서 두 번째 이메일을 발송합니다.
* **발송 실패**
  * 특정 이메일이 발송 실패한 구독자에게 자동 이메일을 보냅니다 '어떤 이메일'에 대한 발송 실패인지 선택할 수 있으며, 이미 발송 완료된 일반 이메일이나 종료된 자동 이메일은 선택할 수 없습니다.
    * 활용 예시: 꼭 받아야 하는 이메일이 발송이 실패한 경우, 자동으로 재발송을 시도합니다.
* **오픈**
  * 특정 이메일을 오픈한 구독자에게 자동 이메일을 보냅니다. 종료된 자동 이메일을 제외한 모든 상태의 이메일을 선택할 수 있습니다.
    * 활용 예시: 캠페인 참여를 요청하는 이메일을 발송합니다. 이 이메일을 오픈한 사람은 캠페인에 어느 정도 관심 있는 사람으로 가정해 캠페인에 대한 추가 정보를 제공하는 이메일을 이어서 발송합니다.
* **오픈 안 함**
  * 특정 이메일을 발송한 뒤 일정 시간이 지날 때까지 그 이메일을 오픈하지 않은 구독자에게 자동 이메일을 보냅니다. 어떤 이메일에 대한 오픈인지, 언제까지 오픈하지 않았을 때 발송할지 선택할 수 있습니다. 이미 발송 완료된 일반 이메일이나 종료된 자동 이메일은 선택할 수 없습니다.
    * 활용 예시: 캠페인 참여를 요청하는 이메일을 발송한 뒤, 오픈하지 않은 사람에게 다시 이메일을 발송합니다.
* **링크 클릭**
  * 특정 이메일에 포함된 링크를 클릭한 구독자에게 자동 이메일을 보냅니다. 어떤 이메일에 대한 클릭인지, 그 이메일의 어떤 링크에 대한 클릭인지 선택할 수 있습니다. 종료된 자동 이메일을 제외한 모든 상태의 이메일을 선택할 수 있습니다.
    * 활용 예시: 신제품을 소개하는 이메일을 발송합니다. 이 이메일에 포함된 신제품 소개 페이지 링크를 클릭한 사람은 구매 의사가 있는 사람이라고 보고, 구매를 유도할 수 있는 구체적인 상품 정보를 제공하는 이메일을 이어서 발송합니다.
* **링크 클릭 안 함**
  * 특정 이메일을 발송한 뒤 일정 시간이 지날 때까지 그 이메일에 포함된 링크를 클릭하지 않은 구독자에게 자동 이메일을 보냅니다. 어떤 이메일에 대한 클릭인지, 그 이메일의 어떤 링크에 대한 클릭인지, 언제까지 클릭하지 않았을 때 발송할지 선택할 수 있습니다. 이미 발송 완료된 일반 이메일이나 종료된 자동 이메일은 선택할 수 없습니다.
    * 활용 예시: 신제품을 소개하는 이메일을 발송합니다. 이 이메일에 포함된 신제품 소개 페이지 링크를 클릭하지 않은 사람은 이 상품에 관심이 없는 사람이라고 보고, 다른 상품을 소개하는 이메일을 발송합니다.

**API 직접 요청**

* API로 직접 요청이 왔을 때 주소록 단계에서 선택한 주소록의 구독자에게 이메일을 발송합니다. 자세한 내용은 [자동 이메일 API 사용하기](api.md) 도움말을 참고해 주세요.
  * 활용 예시: 내 웹사이트에 새로 가입한 회원에게 가입 환영 메일을 발송합니다. 비밀번호 재설정 요청이 도착하면 이메일을 발송합니다.

**카페24 쇼핑몰 전용 트리거**

* **첫 구매 안 함(카페24)**
  * 쇼핑몰 회원가입 후 일정 기간 이내에 구매하지 않았습니다. 첫 구매를 유도하는 이메일을 만들 수 있습니다.
    * 활용 예시: 첫 구매 시에만 사용할 수 있는 여러 혜택에 관한 안내 이메일을 발송합니다.
* **재구매 안 함(카페24)**
  * 쇼핑몰에서 마지막 구매 후 일정 기간 이내에 구매하지 않았습니다. 재구매를 유도하는 이메일을 만들 수 있습니다.
    * 활용 예시: 마지막으로 구매한 'A 제품'과 비슷한 'B 제품'을 추천하거나, 재구매 시 제공되는 혜택 안내 이메일을 발송합니다.
* **상품 구매함(카페24)**
  * 쇼핑몰에서 상품을 구매한 구독자에게 이메일을 보낼 수 있습니다.
    * 활용 예시: 구매한 제품의 자세한 사용법을 알려주거나, 구매평을 작성해 달라고 요청하는 이메일을 발송합니다.

#### **트리거 상세 조건 설정**

원하는 트리거를 설정했다면, 트리거가 동작할 상세 조건을 설정합니다.

* 트리거는 1개 이상 설정할 수 있습니다. 2개 이상 설정하는 경우 여러 개의 트리거를 모두 만족해야 하는지, 하나만 만족해도 되는지 여부를 설정할 수 있습니다.
* 트리거를 만족했을 때 이메일을 바로 발송을 할 수도 있고, 바로 발송하지 않고 몇 시간, 며칠, 몇 주, 몇 년 후에 발송할 수도 있습니다.
* 트리거는 기본적으로 '중복' 발생하는 요청에 대해서는 동작하지 않도록 설정되어 있습니다. 단, 필요에 따라 중복으로 발생한 트리거도 동작할 수 있도록 설정할 수 있습니다.

<figure><img src="../../.gitbook/assets/image (4) (1).png" alt=""><figcaption></figcaption></figure>

#### **트리거 중복 허용하기** <a href="#h_01gqrm1e6ya7vfygdgzmpd8skv" id="h_01gqrm1e6ya7vfygdgzmpd8skv"></a>

자동 이메일 트리거는 기본적으로 중복 요청을 허용하지 않습니다. 중복 발송 요청을 허용하는 경우, 특정 구독자가 조건에 맞는 이메일을 열 때마다 트리거가 작동하여 자동 이메일이 과도하게 발송될 수 있기 때문입니다.

그러나 종종 트리거의 중복 요청을 허용해야 하는 경우가 있습니다. 예를 들어, 스티비를 사용해 회원가입 인증 이메일을 발송하는 경우, 회원이 인증 메일을 여러 번 요청할 수 있습니다. 이때, 트리거 중복 요청을 허용하지 않는다면 회원이 요청할 때마다 인증 메일을 보낼 수 없게 됩니다.

아래 방법으로 \[트리거 중복 허용하기]를 진행할 수 있습니다.

1. 자동 이메일의 \[발송 조건] 설정 단계로 이동합니다.
2.  트리거 설정 아래 쪽에 있는 \[트리거 중복 허용하기]를 활성화합니다. 트리거 중복 요청 활성화를 허용하고 싶지 않은 경우에는 \[트리거 중복 허용하기]를 클릭해 비활성화합니다.

    **\*주의**: '발송 성공, 발송 실패, 오픈 안함, 클릭 안함' 트리거는 \[중복 요청 허용하기] 옵션을 사용할 수 없습니다.

#### **중복 제한 시간 설정하기**

트리거 중복 요청 허용 시간을 제한하는 것도 가능합니다. 동일한 구독자가 특정 시간 안에 트리거 조건을 다시 만족시켰다고 하더라도 이메일을 발송하지 않습니다.

예를 들어, \[오픈] 트리거를 사용하며, 중복 요청 제한 시간을 1시간으로 설정했다면,

* A 구독자가 조건이 되는 이메일을 오전 10:00에 오픈하면, 트리거 조건을 충족했으므로 이메일이 발송됩니다.
* 이후 A 구독자가 이메일을 오전 10:30에 다시 오픈했다면 트리거 중복 허용 제한 시간 설정으로 인해 이메일이 발송되지 않습니다.
* A 구독자가 이메일을 오전 11:10에 다시 한번 오픈했다면 트리거 중복 허용 제한 시간이 이미 지났기 때문에 이메일이 다시 발송됩니다.

_\* 중복 요청 시간 제한을 두고 싶지 않다면 제한 시간을 0분으로 설정하면 됩니다._

<figure><img src="../../.gitbook/assets/자동 이메일 트리거 중복 요청 설정.png" alt=""><figcaption></figcaption></figure>

### **필터** <a href="#schedule" id="schedule"></a>

필터는 트리거 조건을 만족하는 구독자 중 일부에게만 이메일을 발송할 수 있게 하는 조건입니다. 주소록의 \[[그룹](../../list/classify-subscribers/how-to-use-groups.md)] 또는 \[[사용자 정의 필드](../../list/adding-managing-subscriber/understanding-subscriber-info.md)]를 기준으로 설정합니다.

예를 들어, \[링크 클릭] 트리거를 사용해 신제품 소개 이메일 자동 이메일을 설정한 경우,

* 신제품 소개 이메일의 링크를 클릭한 구독자 중 최근 3개월 내 구매 이력이 있는 구독자에게만 이메일을 발송할 수 있습니다.
* 특정 도메인을 사용하는 구독자에게만 이메일을 발송할 수 있습니다.

### **발송 시간대** <a href="#schedule" id="schedule"></a>

발송 시간대는 자동 이메일 발송을 허용하는 시간대입니다. 발송 시간대를 설정하면 트리거와 필터 조건을 만족해도 특정 시간대에만 이메일이 발송되도록 설정할 수 있습니다.

발송 시간대가 아니어서 이메일이 발송되지 않은 경우, 발송 시간대가 돌아올 때까지 기다렸다가 이메일이 발송됩니다.

예를 들어, '월요일 오전 9:00 \~ 수요일 오후 17:00까지만' 이메일이 발송되도록 설정했다면,

* 목요일 오전 9:00에 발송 조건을 충족한 구독자에게는 이메일이 발송되지 않으며, 다음 주 월요일 오전 9:00에 자동으로 이메일이 발송됩니다.

_\* '특정 날짜'에 자동 이메일이 일괄 발송되도록 설정하는 것은 어렵습니다. 특정 시간에 이메일이 발송되도록 설정하고 싶으신 경우라면 '일반 이메일'의 예약 기능을 활용해 주세요._

<figure><img src="../../.gitbook/assets/image (6) (1).png" alt=""><figcaption></figcaption></figure>

#### **발송 시간대의 작동 방식** <a href="#h_01gr12jc8fc1vc8h38887ztpad" id="h_01gr12jc8fc1vc8h38887ztpad"></a>

발송 시간대 기능을 활용하면 구독자가 이메일을 자주 열어보는 시간에만 이메일이 자동 발송되도록 설정할 수 있습니다.

예를 들어, A 자동 이메일 발송 시간대를 '매주 월요일에서 금요일, 매일 오전 10:00 \~ 오후 17:00 까지' 발송되도록 설정했다면,

* A 자동 이메일은 월요일에서 금요일, 오전 10:00 \~ 오후 17:00 까지만 발송됩니다.
* 설정한 발송 시간대가 아닌 시간에는 발송 조건을 만족해도 이메일이 발송되지 않습니다.
* 발송 조건을 월요일 오후 12:00에 만족한 경우, 설정한 발송 시간대에 해당하므로 이메일이 발송됩니다.
* 발송 조건을 일요일 오후 18:00에 만족한 경우 설정한 발송 시간대에 해당하지 않으므로 이메일은 바로 발송되지 않습니다. 가장 빠른 다음 발송 시간대인 월요일 오전 10:00에 자동으로 이메일이 발송됩니다.



발송 시간대 설정은 이메일 성과를 개선할 수 있는 편리한 설정이지만 경우에 따라 발송이 언제 어떻게 진행되는지 헷갈릴 수 있습니다. 아래 사례로 설명드리겠습니다.

**사례 1. 발송 시간대의 시작 시간이 끝 시간보다 큰 경우**

B 자동 이메일의 발송 시간대를 '매일 오후 15:00 \~ 오전 9:00'로 설정했다면,

* B 이메일은 오후 15:00부터 발송을 시작합니다.
* B 이메일의 트리거를 오후 5:00에 만족한 경우 B 이메일은 바로 발송됩니다.
* B 이메일의 트리거를 오전 10:00에 만족한 경우, B 이메일은 가장 빠른 다음 발송 시간대인 오후 3:00에 발송됩니다.
* 즉, 오전 9:01 \~ 오후 14:59까지는 트리거 조건을 만족해도 B 이메일은 발송되지 않으며, 다음날 오전 9:00가 지난 시점에는 트리거 조건을 만족해도 B 이메일은 발송되지 않습니다.

**사례 2. 발송 시간대의 시작 시간이 끝 시간보다 크고, 요일이 제한되어 있는 경우**

C 이메일 발송 시간대를 '월요일 오후 3:00 \~ 화요일 오전 9:00'로 설정했다면,

* C 이메일은 월요일 오후 3:00부터 발송을 시작합니다.
* C 이메일의 트리거를 월요일 오후 5:00에 만족한 경우 C 이메일은 바로 발송됩니다.
* C 이메일의 트리거를 화요일 오전 10:00에 만족한 경우, B 이메일은 가장 빠른 다음 발송 시간대인 다음 주 월요일 오후 3:00에 발송됩니다.
* 즉, 화요일 오전 9:01부터 다음 주 월요일 오후 14:59까지는 조건을 만족해도 C 이메일은 발송되지 않습니다.

### **반복 발송 설정** <a href="#recurring-shipping-settings" id="recurring-shipping-settings"></a>

설정한 주기에 따라 자동으로 이메일이 반복 발송되게 설정할 수 있습&#xB2C8;_&#xB2E4;._

_\* 이 기능을 사용하면 회원의 생일과 같은 기념일을 매년 자동으로 축하해 주거나, 2년에 한 번씩 '광고성 정보 수신 동의'를 받는 이메일 등을 쉽게 설정할 수 있습니다. 자세한 내용은_ [_광고성 정보 수신 동의 여부 정기적으로 확인하기_](../../tip/agree-to-receive-advertising-information.md) _도움말을 참고해 주세요._

<figure><img src="../../.gitbook/assets/image (7) (1).png" alt=""><figcaption></figcaption></figure>

#### **반복 발송 주기 설정하기** <a href="#h_84608cac52" id="h_84608cac52"></a>

반복 발송은 구독자에게 자동 이메일이 처음 발송된 날짜와 시간을 기준으로 설정한 주기에 따라 반복적으로 발송됩니다.

1. \[첫 발송 후 반복 발송하기] 버튼을 클릭해 활성화 상태로 만듭니다.
2. 이메일 반복 주기를 선택합니다.

예를 들어, '매월' 반복 발송되도록 설정하였고, A 사용자에게 자동 이메일이 2025년 2월 1일 오전 9:10에 첫 발송됐다면 다음 발송은 2025년 3월 1일 오전 9:10에 이루어집니다. '매주' 반복 발송되도록 설정하였다면 다음 이메일은 2025년 2월 8일 오전 9:10에 발송됩니다

<figure><img src="../../.gitbook/assets/자동 이메일_4.png" alt=""><figcaption></figcaption></figure>

#### **알아두면 좋을 내용** <a href="#h_70855b93f3" id="h_70855b93f3"></a>

반복 발송 예약 기준은 가장 마지막에 트리거 조건이 충족된 날짜와 시간을 기준으로 결정됩니다.

예를 들어, A 자동 이메일의 발송 조건을 'B 이메일을 오픈한 경우', 매일 반복 발송되도록 설정했다면,

* B 이메일을 수신한 구독자가 2025년 1월 20일 오전 10:00에 이메일을 오픈한 경우, A 이메일이 발송됩니다.
* 또한, A 이메일의 반복 발송 주기에 따라 다음 날 2025년 1월 21일 오전 10:00에 발송이 예약됩니다.
* 그러나 만약 구독자가 2025년 1월 20일 오전 11:00에 이메일을 오픈하여 트리거가 다시 발생하면 다음 반복 발송 시간은 기존에 설정된 2025년 1월 21일 오전 10:00이 아닌 2025년 1월 21일 오전 11:00로 수정됩니다.



## 자동 이메일 ↔ 일반 이메일 변환하기

이메일 목록에서 \[더 보기(v) → 자동/일반 이메일로 변환하기]를 클릭해 자동 이메일을 일반 이메일을 변환할 수 있습니다. 반대로 일반 이메일을 자동 이메일로 변환할 수도 있습니다.

<figure><img src="../../.gitbook/assets/자동 이메일_5.png" alt=""><figcaption></figcaption></figure>

## 이메일 편집하기 <a href="#h_01gh88kw55kz2tzjdfn399rkd2" id="h_01gh88kw55kz2tzjdfn399rkd2"></a>

발송조건을 설정하는 것 이외의 이메일 편집 단계는 일반 이메일과 같습니다. 이메일을 작성하는 자세한 방법은 [이메일 편집하기](using.md#h_01gh88kw55kz2tzjdfn399rkd2) 도움말을 참고해 주세요. 각 단계 제목 앞에 \[V] 표시가 됐다면 모든 단계의 입력을 완료한 것이고, 이제 자동 이메일 발송을 시작할 수 있습니다.
