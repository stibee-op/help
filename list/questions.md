# 자주 묻는 질문

## 구독자 추가하기

<details>

<summary>주소록에 최대로 등록할 수 있는 구독자 수가 궁금해요</summary>

현재 사용 중인 '구독자 수 구간' 내에서 구독자를 등록할 수 있습니다. 화면 오른쪽 뒤 \[워크스페이스 이름]을 클릭하면 사용 중인 요금제에서 등록할 수 있는 최대 구독자 수를 확인할 수 있어요.

_\* 수신거부, 자동삭제, 다른 주소록에 중복 등록된 구독자는 자동으로 구독자 수 계산에서 제외합니다._

#### **스타터 요금제**

무료인 스타터 요금제에서는 최대 500명의 구독자를 등록할 수 있습니다. 500명을 초과하여 구독자를 등록하고 싶다면, 유료 요금제 사용이 필요합니다.

#### **스탠다드, 프로, 엔터프라이즈 요금제**

유료 요금제인 스탠다드, 프로, 엔터프라이즈 요금제를 사용하는 등록할 수 있는 구독자 수 제한이 없습니다. 현재 사용 중인 구독자 수 구간을 초과해 구독자를 등록하고 싶다면, 추가 요금을 지불하신 뒤 구독자 수 구간을 업그레이드 하시면 됩니다.

\[워크스페이스 이름 → 업그레이드 하기 → 요금 구간 변경하기 or 변경하기]를 누른 뒤 표시되는 다음 화면에서 원하시는 구독자 구간을 선택해서 결제할 수 있습니다.

자세한 내용은 [요금제 결제하기](https://docs.channel.io/helpdesk-test/ko/articles/%EC%9A%94%EA%B8%88%EC%A0%9C-%EA%B2%B0%EC%A0%9C%ED%95%98%EA%B8%B0-9c9ed00f) 도움말을 참고해 주세요.

</details>

<details>

<summary>구독자 파일 업로드가 안 돼요</summary>

#### 아래 내용에 따라 단계적으로 어떤 부분이 잘못됐는지 확인하고 빠르게 문제를 해결해 보세요. <a href="#not-possible" id="not-possible"></a>

\[[파일로 추가하기](adding-managing-subscriber/add.md#file)]로 구독자를 추가할 때, 파일이 업로드되지 않을 수 있습니다. 업로드한 파일 내에 구독자 정보가 잘못된 형식으로 저장됐거나, 브라우저 또는 네트워크의 보안 문제을 이유로 파일이 업로드되지 않을 수 있습니다.&#x20;

#### **파일의 형식이 CSV로 잘 저장됐는지 확인해 보세요**

CSV 형식 파일이 아닌 다른 확장자 파일은 업로드할 수 없습니다. 확장자가 CSV인 파일도 저장 과정에서 파일 형식에 오류가 생겼을 수 있습니다. 아래의 방법을 참고해서 파일을 다시 저장한 뒤, 업로드 해보세요.

#### **구독자 정보를 올바른 형식으로 입력했는지 확인해 보세요.**

원본 파일에 잘못된 형식으로 구독자 정보가 입력되어 있으면 파일 업로드가 정상적으로 이루어지지 않을 수 있습니다. 원본 파일에 정보가 잘 입력되어 있는지 확인해 보세요. 샘플 파일을 내려받아 살펴보셔도 좋습니다. ([샘플 파일 내려받기](https://stibee.com/download/%EC%8A%A4%ED%8B%B0%EB%B9%84_%EC%A3%BC%EC%86%8C%EB%A1%9D_%EC%83%98%ED%94%8C.csv))

#### **날짜, 시간 타입 형식을 잘 입력했는지 확인해 보세요.**

날짜, 시간 타입은 지원하는 형식이 있습니다. 8자리(날짜), 12자리(날짜와 시간), 14자리(날짜와 시간) 형식을 지원합니다.

**\*주의:** 시간은 24시간 기준으로 입력해야 합니다. 예를 들어, 2023년 9월 20일 오후 5시 25분 15초를 추가하고 싶다면, 2023-09-20 17:25:15 형식으로 입력해야 합니다.

<pre><code><strong>지원하는 형식
</strong>
- 8자리
yyyy-MM-dd (예: 2023-01-24)
yyyy/MM/dd (예: 2023/01/24)
yyyy.MM.dd (예: 2023.01.24)
yyyy MM dd (예: 2023 01 24)
yyyyMMdd   (예: 20230124)

- 12자리
yyyy-MM-dd HH:mm (예: 2023-05-13 11:00)
yyyy/MM/dd HH:mm (예: 2023/01/24 11:00)
yyyy.MM.dd HH:mm (예: 2023.01.24 11:00)
yyyy MM dd HH:mm (예: 2023 01 24 11:00)
yyyyMMdd HH:mm   (예: 20230124 11:00)
yyyyMMddHHmm     (예: 202301241122)

- 14자리
yyyy-MM-dd HH:mm:ss (예: 2023-08-09 14:15:20)
yyyy/MM/dd HH:mm:ss (예: 2023/08/09 14:15:20)
yyyy.MM.dd HH:mm:ss (예: 2023.08.09 14:15:20)
yyyy MM dd HH:mm:ss (예: 20203 08 09 14:15:20)
yyyyMMdd HH:mm:ss   (예: 202030809 14:15:20)
yyyyMMddHHmmss      (예: 202030809141520)
</code></pre>

#### **파일 용량을 확인합니다.**

업로드할 수 있는 파일의 용량을 **50MB**로 제한하고 있습니다. 더 큰 용량의 파일로 구독자를 추가해야 한다면, 50MB 이내로 파일을 쪼개어 업로드하는 것을 권장합니다. 이메일 주소만 입력되어 있다고 가정했을 때 50MB는 약 250만 행에 해당합니다.

#### **원본 파일의 모든 필드가 \[사용자 정의 필드] 별로 올바르게 선택됐는지 확인해 보세요.** <a href="#h_01h0s8dz775dyr4awtwwed30xp" id="h_01h0s8dz775dyr4awtwwed30xp"></a>

파일 형식, 용량, 원본 파일에 문제가 없는데 파일 업로드가 되지 않는다면, 파일 업로드 단계에서 원본 파일 필드와 \[사용자 정의 필드]가 잘 선택되어 연결됐는지 확인해 보세요.

#### **'시크릿 모드'에서도 문제가 계속되는지 확인해 보세요.**

종종 브라우저에서 사용하는 확장 프로그램이 정상적인 기능 동작을 방해하는 경우가 있습니다. 브라우저를 '시크릿 모드' 상태로 바꾼 뒤, 파일을 업로드 해보면 확인할 수 있습니다. 시크릿 모드에서는 파일이 업로드된다면 브라우저의 확장 프로그램 문제일 가능성이 높습니다. 확장 프로그램을 하나씩 비활성화해 보면서 어떤 프로그램이 원인인지 확인해 보아야 합니다.&#x20;

#### **다른 네트워크에서 파일을 업로드해 보세요.** <a href="#h_01h0s8e9y2k88jvtgnjjp6rtjg" id="h_01h0s8e9y2k88jvtgnjjp6rtjg"></a>

네트워크 보안 설정을 이유로 파일 업로드에 제한이 걸리는 경우가 있습니다. 지금 사용하는 네트워크가 아닌 다른 네트워크(예: 핸드폰 테더링 등)에서 파일을 업로드 해보면 이를 확인하실 수 있습니다. 다른 네트워크에서는 파일이 정상적으로 업로드된다면 네트워크 보안 문제일 가능성이 높습니다. 이 경우 내부 보안 관리자분께 문의해 보시면 빠르게 문제를 해결하실 수 있습니다.

</details>

<details>

<summary>연동 주소록과 일반 주소록은 어떤 차이가 있나요?</summary>

스티비는 일반 주소록, 유료 구독 주소록, 연동 주소록 총 3가지 주소록을 제공하고 있습니다. 3가지 주소록은 기능에 차이가 있으므로 사용 목적에 따라 주소록 종류를 선택해서 사용해야 합니다.

* [일반 주소록](broken-reference): 구독자를 추가하고 관리할 수 있는 일반적인 기능을 제공하는 주소록입니다.
* [유료 주소록](broken-reference): 유료 뉴스레터를 운영할 때 유료 구독자를 관리할 수 있는 기능을 제공하는 주소록입니다.
* [연동 주소록](broken-reference): 카페24, NHN커머스, 식스샵 등 외부 솔루션을 통해 만든 온라인 홈페이지가 있는 경우 연동해서 사용할 수 있는 주소록입니다. 연동된 온라인 홈페이지의 회원 정보를 자동으로 불러옵니다.

</details>

<details>

<summary>'상태 외 정보 업데이트'라고 하면서 구독자가 추가되지 않아요.</summary>

이미 주소록에 존재하는 이메일 주소의 구독자를 다시 추가한 경우 추가 결과가 [상태 외 정보 업데이트](adding-managing-subscriber/add.md#results-of-adding)로 표시됩니다.

이미 존재하는 구독자를 다시 추가한 경우에는 중복으로 구독자가 추가되는 것이 아니라 이메일 주소를 제외한 나머지 정보(예: 이름, 연락처 등)이 가장 마지막에 등록한 정보를 기준으로 업데이트 됩니다.

</details>

<details>

<summary>파일로 추가할 때 수신거부 상태로 추가할 수 있나요?</summary>

수신거부에 대한 값을 CSV 파일에 미리 입력하면, 구독자를 파일로 추가할 때 수신거부 상태로 추가할 수 있습니다.

1. CSV 파일에서 수신거부 여부를 표시할 열을 추가합니다. 수신거부 상태로 추가할 구독자는 이 열에 Y를 입력합니다.
2. 구독자 정보가 주소록의 어떤 항목에 해당하는지 선택할 때, 수신거부에 대한 값을 입력한 열을 수신거부 항목으로 선택합니다.&#x20;
3. 수신거부 항목으로 선택된 열에 Y가 입력되어있으면, 그 구독자는 수신거부 상태로 추가됩니다. 만약 이미 등록된 구독자라면, 수신거부 상태로 변경됩니다.

자세한 내용은 [#h\_01gfam9r8typybhwpebnjf382c](adding-managing-subscriber/add.md#h_01gfam9r8typybhwpebnjf382c "mention") 도움말을 참고해 주세요.

</details>

## 구독자 목록

<details>

<summary>수신거부, 자동삭제 된 명단을 어디서 확인할 수 있나요?</summary>

확인하고자 하는 주소록을 선택한 뒤 \[구독자 목록 → 구독 중 필터]를 클릭하면 '구독 중, 수신거부, 자동삭제' 등 구독 상태별로 체크하여 확인할 수 있습니다.&#x20;

자세한 내용은 [구독 상태 필터](adding-managing-subscriber/search-subscriber.md#h_01gfaq4cjqw7jtcp26af3cpf4y-1) 도움말을 참고해 주세요.

</details>

<details>

<summary>여러 주소록에 있는 구독자가 수신거부한 경우 어떻게 되나요?</summary>

수신거부는 기본적으로 각 주소록 단위에서 관리됩니다. 예를 들어 dooly@stibee.com 구독자가 A, B 두개의 주소록에 등록되어 있고 A 주소록에 발송한 이메일에서 수신거부를 했다면,&#x20;

* A 주소록에 등록된 dooly@stibee.com의 구독 상태는 \[수신거부]로 변경됩니다.
* B 주소록에 등록된 dooly@stibee.com의 구독 상태는 그대로 \[구독 중] 상태로 유지됩니다.

이 경우 구독자 수 계산은 만약에 A, B 두 주소록에 모두 dooly@stibee.com이 '구독 중' 상태로 등록되어 있다면 자동으로 중복은 제거되고 1명으로 계산됩니다.&#x20;

만약에 위 사례처럼 dooly@stibee.com이 한 주소록에서만 수신거부로 처리가 됐다고 해도 아직 B 주소록에는 '구독 중' 상태로 남아있기 때문에 이 경우 dooly@stibee.com 구독자는 마찬가지로 1명으로 계산됩니다. 구독자 수 계산에서 dooly@stibee.com을 제외하고 싶다면 A,B 두 주소록에서 모두 '수신거부' 상태로 변경되어야 합니다.

</details>

<details>

<summary>구독자가 구독 정보를 직접 변경할 수 있나요?</summary>

구독 정보 변경 화면에서 구독자가 자신의 구독 정보를 직접 변경할 수 있습니다. 구독 폼의 구독 확인 메시지나 구독 확인 화면 등의 링크를 통해서 구독자가 구독 정보 변경 화면에 접근할 수 있습니다.

자세한 내용은 [구독자가 직접 변경하기](adding-managing-subscriber/modify-subscriber-info.md#h_01gfaz1dqx7jfb1mr5w6myba1t) 도움말을 참고해 주세요

</details>

## 사용자 정의 필드

<details>

<summary>정보가 입력된 사용자 정의 필드의 유형을 변경하면 어떻게 되나요?</summary>

필드 유형을 변경해도 구독자별로 저장된 정보가 사라지지는 않습니다. 다만, 변경한 구독 유형 종류에 따라 유형을 변경하는 경우 필드 옵션 설정 값이 초기화될 수 있습니다.

* 드롭다운, 라디오버튼 유형 → 텍스트 유형으로 변경하는 경우 기존에 사용하던 드롭다운, 라디오 버튼의 옵션 설정 값(예: 유입 채널 - 구글, 페이스북 등)은 텍스트 유형으로 변경하게 되면 초기화됩니다.
* 드롭다운, 라디오버튼 유형 → 드롭다운, 라디오 버튼 유형으로 변경하는 경우는 기존에 설정한 필드의 옵션 설정 값이 그대로 유지됩니다.

</details>

<details>

<summary>필드의 유형을 변경하면 구독자 정보도 바뀌나요?</summary>

이미 저장된 정보는 필드 유형을 변경해도 바뀌지 않습니다.&#x20;

단, 필드를 삭제하는 경우에는 기존에 각 필드에 저장된 정보는 모두 삭제되고 복구가 불가능하니 유의해 주세요.

</details>

<details>

<summary>드롭다운, 라디오 버튼 유형의 옵션 값은 몇 개까지 추가할 수 있나요?</summary>

드롭다운과 라디오 버튼은 둘 모두 최대 20개까지 추가할 수 있습니다. 관리자가 설정 가능한 각 옵션값의 최대 수는 13자로 제한되어 있습니다.&#x20;

단, \[라디오 버튼 → 기타] 옵션을 사용해서 구독자가 제출하는 답변은 글자수 제한이 없습니다.

</details>

<details>

<summary>주소록을 만들 때 회사/단체명, 주소, 연락처를 입력하는 이유가 궁금해요.</summary>

정보통신망법에 따라 영리 목적의 광고성 정보를 포함한 이메일은 본문에 전송자의 명칭, 전화번호 및 주소를 표시해야 합니다. 이를 지키지 않으면 과태료 부과 및 형사 처분의 대상이 될 수 있습니다.

_영리 목적의 광고성 정보란? 이메일을 보내는 사람이 경제적 이득을 취할 목적으로 보내는 자기 자신에 대한 정보나 보내는 사람이 제공할 재화나 서비스의 내용을 말합니다._

하지만 이는 일반적인 내용일 뿐이고 영리 목적의 광고성 정보에 해당하는지 여부는 사안마다 다릅니다. 따라서 보내는 사람이 누구인지, 보내는 내용이 무엇인지에 따라 세심하게 검토할 필요가 있습니다. 만약, 관련해 자문이 필요한 경우 한국인터넷진흥원(KISA) 측으로 문의해 보시는 것을 추천드립니다.

* 유선 연락처: 118
* 사이트: [https://www.kisa.or.kr/cyberhelper118](https://www.kisa.or.kr/cyberhelper118)

주소록을 만들 때 입력한 회사/단체명, 주소, 연락처는, 이메일을 만들 때 콘텐츠에서 푸터 상자를 추가하면 자동으로 추가됩니다. 추가된 푸터 상자의 회사/단체명, 주소, 연락처는 수정하거나 속성을 변경할 수 있습니다.&#x20;

</details>
