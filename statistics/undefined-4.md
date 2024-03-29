# 자주 묻는 질문



<details>

<summary>이상한 이메일 주소에서 오픈, 클릭이 일어났어요</summary>

## 언제 필요한가요? <a href="#h_01hhen67k8cs5vtqmry6yqghjn" id="h_01hhen67k8cs5vtqmry6yqghjn"></a>

* gmai.com, gmil.com, hanmai.net 등 이상한 도메인을 사용하는 구독자로부터 오픈, 클릭 기록이 존재하는 경우

&#x20;

종종 이메일을 보내고 나서 오픈, 클릭 기록을 확인했을 때 정상적이지 않은 도메인을 사용하는 구독자 임에도 불구하고 오픈, 클릭 기록이 존재하는 경우가 있습니다. 보통 이 문제는 대부분의 사람들이 많이 사용하는 도메인(예: gmail.com, naver.com)과 비슷한 도메인(예:gmai.com, nacer.com 등)을 사용하는 구독자인 경우가 많습니다.\
\
일반적으로 많이 사용하는 도메인과 비슷한 도메인을 특정 목적으로 구입해서 이 도메인을 사용하는 이메일 주소로 이메일 수신이 가능하도록 설정해 두는 경우가 있습니다. 비슷한 도메인을 구입해서 수신이 가능하도록 설정하는 목적은 스팸성 이메일 발송 또는 특정 정보 수집을 위한 목적 등 원인은 다양할 수 있습니다. \
\
따라서 정상적이지 않은 것으로 판단되는 이메일 주소는 \[[수신거부](https://help.stibee.com/hc/ko/articles/4756415150607)]로 처리하거나 주소록에서 완전히 [삭제](https://help.stibee.com/hc/ko/articles/5673136659471-%EA%B5%AC%EB%8F%85%EC%9E%90-%EC%A0%95%EB%B3%B4-%EC%88%98%EC%A0%95%ED%95%98%EA%B8%B0#h\_01GFAZ23XCPZGHH2CBPS07SM97)하여 이메일이 앞으로 발송되지 않도록 조치를 취하는 것이 좋습니다.&#x20;

\


</details>

<details>

<summary>소프트바운스, 하드바운스가 뭔가요?</summary>

### 언제 필요한가요?

* 이메일 발송이 실패한 이유가 궁금할 때
* 소프트바운스, 하드바운스로 분류되는 기준이 궁금할 때

&#x20;

이메일을 보낸다고 모두 잘 도착하는 것은 아닙니다. 일부는 도착하지 않기도 하죠. 이메일이 발송 실패되는 경우를 '반송, 바운스(Bounce)'라고 합니다. 바운스는 발송실패 이유에 따라 '소프트바운스(Soft bounce)'와 '하드바운스(Hard bounce)'로 나뉩니다.&#x20;

\
발송 결과는 이메일을 받아본 수신 서비스(예: 네이버, G메일, 카카오, 그룹웨어 등)에서 스티비로 어떤 응답 값을 회신하는지를 기준으로 판단합니다. 발송 요청 결과, 수신 서비스에서 어떤 값을 회신하는지 여부에 따라 '발송 성공'과 '발송 실패'로 분류되고 '발송 실패'는 다시 실패 사유에 따라 '소프트바운스'와 '하드바운스'로 분류됩니다.

### 소프트바운스

소프트바운스는 이메일을 '일시적으로 전달할 수 없는 경우'입니다. 소프트바운스는 보통 일시적인 문제일 가능성이 높기 때문에 여러 차례 다시 시도하면 해결됩니다. 다만 다시 발송을 여러 차례 시도했음에도 불구하고 계속해서 발송이 실패하는 경우, 구독자의 상태가 이메일 수신이 불가능한 상태일 수 있습니다. 이런 경우에는 구독자를 별도의 \[[그룹](https://help.stibee.com/hc/ko/articles/4756567819791)]으로 분류하여 관리하거나 \[주소록]에서 삭제하는 것이 좋습니다.

_\*소프트바운스로 발송 실패한 구독자에게 이메일을 재발송하는 방법이 궁금하다면_ [_여기_](https://help.stibee.com/hc/ko/articles/4756487318927)_를 참고해주세요._ \
\
소프트바운스는 상세 사유에 따라 몇가지로 구분될 수 있습니다.&#x20;

* 소프트바운스: 일시적인 문제로 이메일 발송에 실패했습니다.&#x20;
* 소프트바운스(응답지연): 이메일 수신 서비스에서 발송 결과를 스티비로 회신하지 않았습니다. 수신 서비스의 이메일 처리에 문제가 있는 상황일 수 있기 때문에 구독자 측의 이메일 서비스 담당자 또는 고객센터로 문의해보면 정확한 원인 파악이 가능합니다.
* 소프트바운스(메일함 용량 부족): 구독자의 메일함 용량이 꽉차 발송에 실패했습니다.
* 소프트바운스(알 수 없음): 이메일 발송에 실패했으나 정확한 사유를 확인하기 어렵습니다. '소프트바운스(알 수 없음)'으로 분류되는 비율을 줄이기 위해 판단 기준은 계속해서 업데이트하고 있습니다. &#x20;

### 하드바운스

하드바운스는 구독자의 이메일 계정 상태가 이메일을 영구적으로 수신할 수 없는 경우(예: 탈퇴한 이메일 계정, 유효하지 않은 이메일 주소 등)를 말합니다. 하드바운스로 발송 실패한 이메일 주소는 유효하지 않은 주소이기 때문에 \[주소록]에서 삭제하거나 따로 분류하는 것이 좋습니다. \
\
하드바운스는 다시 실패 사유에 따라 몇 가지로 구분될 수 있습니다.&#x20;

* 하드바운스: 구독자가 현재 영구적으로 이메일을 수신할 수 없는 상태입니다.
* 하드바운스(이메일 주소 없음): 이메일 주소가 잘못됐거나 존재하지 않는 주소입니다.
* 하드바운스(스팸처리됨): 수신자가 이메일을 스팸 메일로 처리했습니다.

스티비는 하드바운스 된 이메일 주소를 '[자동삭제](https://help.stibee.com/hc/ko/articles/5013280388623)'로 분류하여 이후의 발송 대상에서 제외합니다. 이렇게 하면 발송성공률이 개선되고 비정상적인 발송을 피할 수 있기 때문에 스팸으로 분류될 확률도 줄어듭니다.\
\
만약, 하드바운스된 이메일 주소가 자동삭제로 자동 분류되는 것을 원하지 않는다면 \[주소록 → 수정하기 → 자동삭제 기능 사용 유무]를 '아니요'로 선택하면 됩니다. 주소록을 수정하는 자세한 방법에 대한 내용은 [여기](https://help.stibee.com/hc/ko/articles/5659543793551-%EC%A3%BC%EC%86%8C%EB%A1%9D-%EC%82%AC%EC%9A%A9%ED%95%98%EA%B8%B0#h\_01GF88JFX86W5EWKKK27BDP48J)를 참고해주세요.

</details>

<details>

<summary>오픈이 없는데 클릭 기록이 있는 구독자가 있어요.</summary>

### 언제 필요한가요?

* 이메일 통계에서 오픈 기록은 없는데 클릭 기록은 존재하는 구독자가 있는 경우

&#x20;

스티비의 \[오픈]은 구독자가 이메일을 열어본 경우에 추적됩니다. 다만 종종 \[오픈]기록은 없지만 이메일의 \[클릭]기록은 있는 구독자가 존재할 수 있습니다. 이런 경우는 크게 두가지 경우를 의심해볼 수 있습니다.

#### 이메일 본문에 삽입된 추적용 이미지가 로드되지 않았습니다.

스티비에서는 \[오픈] 추적을 위해 이메일 본문에 추적용 이미지를 삽입합니다. 대부분 문제가 없지만 종종 일부 수신 환경(예: 기업 메일, 아웃룩 등)에서는 임의로 추적용 이미지를 이메일 본문을 불러오는 과정에서 로드하지 않는 경우가 있습니다. 또는 종종 사용자의 설정에 따라 이미지를 불러오지 않는 경우도 있습니다. 이런 경우 실제로 구독자가 이메일을 열어봤지만 추적용 이미지를 불러오지 않았기 때문에 \[오픈]기록이 추적되지 않을 수 있습니다.\
\
\[오픈] 추적은 이루어지지 않았지만 실제로 구독자가 이메일을 열어본 경우이기 때문에 \[클릭]기록은 존재할 수 있습니다.

#### &#x20;수신 서비스의 스팸봇이 이메일 콘텐츠를 검사하는 과정에서 링크를 클릭했습니다.

수신 서비스(예: G메일, 네이버 등)들에서는 이메일 수신자에게 스팸 메일이 전달되지 않도록 자체적인 스팸 필터링 시스템을 통해 이메일이 스팸인지 아닌지 여부를 판단합니다. 이때 이메일의 내용의 스팸성 여부를 판단하기 위해 스팸봇이 이메일의 링크를 클릭하는 경우가 있습니다. 이런 경우 실제 구독자의 \[클릭] 이 아니지만 \[클릭]으로 추적되는 경우가 있습니다.\
\
스팸봇에 의한 \[클릭]추적을 방지하기 위해 주기적으로 \[클릭]기록을 확인하여 분류 기준을 업데이트하고 있습니다. 정확한 통계를 제공할 수 있도록 계속해서 노력하겠습니다.

</details>

<details>

<summary>일정 기간 동안 오픈, 클릭 기록이 없는 구독자를 확인하고 싶어요.</summary>

💬 이 내용은 **스탠다드 요금제**에 해당하는 도움말입니다.

### &#x20;언제 필요한가요?

* 이메일을 오랫동안 오픈하거나 클릭한 기록이 없는 구독자 명단을 확인하고 싶을 때

주소록의 \[[통계 생성하기](https://help.stibee.com/hc/ko/articles/4756459860111)]를 사용하면 일정 기간 동안 오픈이나 클릭 기록이 없는 구독자 명단을 조회할 수 있습니다. 조회한 명단을 주소록 \[[그룹](https://help.stibee.com/hc/ko/articles/4756567819791)]으로 등록해 별도로 분류해 관리하는 것도 가능합니다.

1. 메인화면 위에 있는 메뉴에서 \[주소록]을 클릭해 주소록 목록으로 이동합니다.
2. 목록에서 \[오픈], \[클릭] 기록이 없는 구독자를 걸러내고 싶은 주소록을 선택합니다.
3. 구독자 목록 오른쪽 위에 있는 \[내보내기 → 통계 생성하기]를 클릭해 기간을 설정해서 통계를 생성한 뒤 파일을 내려받습니다.
4. 파일을 열어 \[오픈], \[클릭] 필드의 값이 0인 구독자를 필터 기능을 사용해 조회합니다.

</details>

<details>

<summary>이메일 통계는 얼마 동안 추적되나요?</summary>

### 언제 필요한가요?

* 이메일 통계를 추적하는 기간이 궁금한 경우

이메일 통계는 계속해서 집계되며 따로 정해진 기간은 없습니다. \[[오픈](https://help.stibee.com/hc/ko/articles/4894585402383)], \[[클릭](https://help.stibee.com/hc/ko/articles/4894564542863)]이 중복으로 일어난 경우 '상세통계'에는 마지막으로 오픈 또는 클릭이 일어난 시간을 기준으로 기록됩니다. 어떤 구독자가 가장 처음 이메일을 오픈하거나 클릭한 시간을 알고 싶은 경우에는 [구독자 별 통계](https://help.stibee.com/hc/ko/articles/4756514418063)를 참고하면 확인할 수 있습니다.\
\
\*이메일을 발송한 뒤에 구독자 정보를 삭제하게 된다면 통계 기록에 문제가 생길 수 있습니다.\
스티비의 이메일 통계는 구독자를 기준으로 기록됩니다.  오픈, 클릭 이벤트가 발생했을 때 기록할 구독자 정보가 주소록에 존재하지 않는다면 통계를 기록할 대상이 사라져 결과 표시에 문제가 발생합니다.&#x20;

</details>
