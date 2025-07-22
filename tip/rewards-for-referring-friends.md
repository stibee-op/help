# 친구를 초대한 구독자에게 보상 주기

💬 이 내용은 **스탠다드, 프로, 엔터프라이즈 요금제**에 해당하는 도움말입니다.

## 언제 필요한가요?

* 스티비 \[[구독 폼](../list/gather-subscribers/form.md)]을 사용해 구독 신청을 받는 경우
* 구독자에게 전용 초대 링크를 제공해서 성과를 측정하고 싶은 경우
* 친구를 많이 초대한 구독자에게 보상을 제공하고 싶은 경우

***

\[사용자 정의 필드]와 \[메일머지]를 활용하면 누가 가장 많은 친구를 초대했는지 확인할 수 있습니다. 가장 많은 친구를 초대한 구독자에게 보상을 제공하거나 별도 \[그룹]으로 분류해 감사 메일을 보내면, 구독자와의 관계를 관리하는 데 도움을 받을 수 있습니다.



## 준비하기 <a href="#h_c58b87726b" id="h_c58b87726b"></a>

\[주소록 → 사용자 정의 필드]에서 '어떤 구독자가 친구를 초대했는지' 결과를 기록할 수 있는 \[사용자 정의 필드]를 생성합니다. 만약 'A'라는 구독자를 통해 B라는 구독자가 구독을 신청했다면, 'B라는 구독자는 A가 추천해서 입력된 사람이다'를 알고 있어야 적절한 보상을 제공할 수 있습니다. 이 정보를 기록할 필드를 주소록에 새롭게 만듭니다. 어떤 필드를 만들어야 할지 고민이 된다면 우선 아래 예시를 참고해서 새로운 필드를 만들어 보세요.&#x20;

* 필드 이름: 추천인
* 키(Key): recommender&#x20;

<figure><img src="https://downloads.intercomcdn.com/i/o/525589764/f3b1579f88f069fefcf5069e/%EC%82%AC%EC%9A%A9%EC%9E%90%EC%A0%95%EC%9D%98%ED%95%84%EB%93%9C%ED%8C%8C%EB%9D%BC%EB%AF%B8%ED%84%B0_1.gif" alt=""><figcaption></figcaption></figure>

## 구독자별 고유 친구 초대 링크 만들기 <a href="#h_01hhdt9npt2073j2x0na6zfh8x" id="h_01hhdt9npt2073j2x0na6zfh8x"></a>

필드를 만들었다면 구독자가 본인의 친구를 초대할 때 사용할 수 있는 고유 추천 링크를 만듭니다. 구독자가 누구에게 추천받고 들어왔는지는 이 구독자가 어떤 URL을 통해 구독 폼에 접속해서 구독 신청을 했는지에 따라 달라집니다. 따라서 모든 구독자에게 저마다 '서로 다른 고유한 추천 링크'를 제공해야 합니다.\
\
스티비 \[구독 폼]을 사용하지 않는다면 구독자의 수만큼 전용 링크를 만들어야 하고 매번 늘어날 때마다 수기로 새로운 링크를 만들어 제공해야 합니다. (예: 구독자가 10,000명이라면 10,000개의 고유한 추천 링크가 필요합니다.)\
\
그러나 스티비의 \[메일머지]와 \[구독 폼]을 사용하면, 하나의 URL만 잘 만들면 매번 새로운 URL을 만들 필요 없이 모든 구독자에게 고유한 추천 링크를 간단하게 만들어 제공할 수 있습니다.



### 구독 폼 URL의 형식 <a href="#h_01heh92jswr9aeft9bcf65wjc5" id="h_01heh92jswr9aeft9bcf65wjc5"></a>

스티비 구독 폼은 기본적으로 아래와 같은 형식으로 구성됩니다. '{list\_id}'는 각 주소록에 부여되는 고유한 ID 값입니다. \[주소록 → 대시보드]로 이동해 화면의 URL을 확인하면 중간에 숫자가 있습니다. 이 숫자가 list\_id 값입니다. list id를 확인해 아래처럼 URL을 생성해 주세요.&#x20;

\* _https://stibee.com/lists/**nnnnnn**/dashboard 에서 'nnnnnn'이 list\_id 값입니다._

* 스티비 구독 폼 기본 형식: https://page.stibee.com/subscriptions/{list\_id}
  * <스요레터>, [https://page.stibee.com/subscriptions/3](https://page.stibee.com/subscriptions/3)
  * <비레터>, [https://page.stibee.com/subscriptions/62723](https://page.stibee.com/subscriptions/62723)



### 구독자별 고유 추천 URL의 형식 <a href="#h_01heh92jsws1e19r2xjw2xts9s" id="h_01heh92jsws1e19r2xjw2xts9s"></a>

구독자별 고유 추천 링크는 기본적인 구독 폼 형식에 몇 가지 값을 추가해 주면 됩니다. 구독 폼 뒤에 형식에 맞는 값을 직접 입력하면 됩니다.&#x20;

* https://page.stibee.com/subscriptions/{list\_id}**?field\_key={field\_value}**&#x20;

기본 구독 폼 형식에서 굵은 글씨로 표시된 부분이 추가된 것을 확인할 수 있습니다. 각 값이 가지는 의미는 아래와 같습니다.

* ? : 구독 폼 URL과 고유한 링크를 생성하기 위해 사용자가 임의로 추가하는 값을 구분해서 표시하기 위한 목적으로 사용하는 구분자입니다.&#x20;
* field\_key: \[사용자 정의 필드]의 추천인 정보가 입력될 필드의 키 값을 입력하면 됩니다. 이 키 값을 기준으로 주소록에 정보가 등록되게 됩니다.
* field\_value: 친구를 추천한 구독자를 '식별할 수 있는 정보'가 들어가는 부분입니다. 여기에 구독자별로 고유한 값이 자동으로 변환되어 입력되도록 설정하면 됩니다. 이메일 주소를 활용할 수도 있고, 개별 코드로 치환되도록 설정할 수도 있습니다.

### 초대 결과 확인하기 <a href="#h_01hfdxk57w2s3refh0z4mqs7yv" id="h_01hfdxk57w2s3refh0z4mqs7yv"></a>

이제 위 설명을 참고해서 구독자별 고유 추천 URL을 만들어 주면 됩니다. list\_id는 가지고 있는 주소록의 값에 맞게 직접 수정해 주세요.

*   https://page.stibee.com/subscriptions/{list\_id}?**recommender=$%email%$**

    \
    **\*주의:** 도움말에서는 이메일 주소를 field value로 활용하고 있지만, 일부 디바이스 환경(예: 카카오톡 등)에서는 이메일 주소를 field value로 활용할 경우 '구독자별 고유 추천 URL'이 제대로 동작하지 않을 수 있습니다. 이 경우 이메일 주소가 아닌 별도의 코드를 만들어 구독자를 식별해 사용하면 됩니다.



### 구독자에게 전용 초대 링크 알려주기 <a href="#h_01hf3tq1ax93dhsa5t6nwnrdmf" id="h_01hf3tq1ax93dhsa5t6nwnrdmf"></a>

구독자별 초대 링크 형식을 만들었다면 이제 구독자에게 전용 초대 링크를 안내하고, 친구를 초대해 달라고 요청하면 됩니다.

1. \[이메일]을 새롭게 생성합니다.
2. 추천인 링크로 연결되는 버튼이나 텍스트를 본문에 추가합니다.\
   예) 친구에게 구독 폼 공유하기
3. 2에서 추가한 버튼 또는 텍스트의 링크에 생성한 고유 초대 링크를 입력합니다.\
   예: https://page.stibee.com/subscriptions/{list\_id}/?recommender=$%email%$
4. 이메일을 발송합니다.

이메일을 발송하면 고유 초대 링크의 $%email%$이 구독자별 고유한 값으로 변환되어 발송됩니다. dooly@stibee.com이라는 구독자에게 고유 초대 링크를 발송했다면 아래 예시와 같이 변환됩니다.

* 작성 시: https://page.stibee.com/subscriptions/{list\_id}/?recommender=$%email%$
* 발송 시: https://page.stibee.com/subscriptions/{list\_id}/?recommender=dooly@stibee.com

고유 초대 링크를 구독자들에게 보내고 시간이 지나면 특정 구독자를 통해 추천받은 구독자들이 주소록에 등록됩니다. 어떤 구독자에게 추천받아 등록된 구독자인지 여부를 확인하기 위해서는 주소록의 '추천인' 필드에 누구의 이메일 주소가 등록됐는지 확인하면 됩니다.\
\
만약, dooly@stibee.com라는 구독자가 gildong.go@stibee.com라는 이메일 주소를 사용하는 친구를 초대했다면 gildong.go@stibee.com이라는 구독자의 '추천인' 필드 정보에는 dooly@stibee.com이 기록됩니다.

<figure><img src="../.gitbook/assets/image (114).png" alt=""><figcaption></figcaption></figure>



### 보상 제공하기 <a href="#h_01hhdw8czczvb1v5hkxykf562k" id="h_01hhdw8czczvb1v5hkxykf562k"></a>

보상을 제공하기 위해서는 어떤 구독자가 가장 많이 추천했는지 여부를 확인해야 합니다. 이때는 스티비의 \[필터] 기능을 사용해 '추천인' 필드의 구독자 정보를 기준으로 정렬해 확인하거나 확인해야 하는 숫자가 많은 경우 구독자 목록을 \[파일로 내보내기] 한 뒤 '추천인' 필드를 기준으로 파일에서 필터를 걸어 확인하는 방법도 있습니다.

필터를 걸어 가장 많이 추천한 구독자에게는 별도의 포인트를 제공하거나 일정 횟수 이상 추천한 구독자는 별도 \[그룹]으로 분류해 감사 이메일을 보내보세요.

_실제로 사용하는 사례는 블로그의_ [_주말랭이가 추천인 제도를 운영하는 방법_](https://blog.stibee.com/ec-a3-bc-eb-a7-90-eb-9e-ad-ec-9d-b4-ea-b0-80-ec-b6-94-ec-b2-9c-ec-9d-b8-ec-a0-9c-eb-8f-84-eb-a5-bc-ec-9a-b4-ec-98-81-ed-95-98-eb-8a-94-eb-b0-a9-eb-b2-95/)_에서 확인할 수 있어요._
