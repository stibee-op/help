---
layout:
  title:
    visible: true
  description:
    visible: false
  tableOfContents:
    visible: true
  outline:
    visible: true
  pagination:
    visible: true
---

# 구독료 변경하기

### **💬** 이 내용은 **스탠다드 요금제**에 해당하는 도움말입니다.

&#x20;

유료 구독 주소록을 만들 때 설정한 구독료는 언제든 변경할 수 있습니다. 구독료를 변경하고 싶은 유료 구독 주소록의 정보 수정 화면에서 구독료를 변경할 수 있습니다.\
\
유료 구독료 변경 기능을 사용하면 특정 기간 동안 결제한 구독자는 할인된 금액으로 계속 이용할 수 있는 일종의 '얼리버드' 혜택을 제공하는 것도 가능합니다.

&#x20;

### 구독료 변경하기 <a href="#h_0e56d186cc" id="h_0e56d186cc"></a>

구독료를 변경하고 싶은 유료 구독 주소록을 선택하고 주소록의 대시보드에서 \[수정하기]를 클릭합니다.

![](https://help.stibee.com/hc/article\_attachments/4756483739151/6270c032e0b91.png)

\
유료 구독 정보 - '구독 상품'에서 월간 구독료와 연간 구독료를 수정하고 페이지 하단 \[저장하기]를 클릭합니다.

![](https://help.stibee.com/hc/article\_attachments/4756483755023/6270c03493798.png)&#x20;

### 구독료 변경에 따른 구독자 결제 금액 <a href="#h_2ba5fdfc62" id="h_2ba5fdfc62"></a>

구독료를 변경하면 변경하기 전에 결제한 구독자는 '변경 전 금액'으로 결제되며, 변경한 후에 결제한 구독자는 '변경된 금액'으로 결제가 진행됩니다.\
\
예를 들어, 3월 1일에 구독료를 5,000원으로 설정한 유료 구독 주소록을 만들었고 3월 10일에 구독료를 10,000원으로 변경한 상황을 가정해보겠습니다. 구독자 A는 3월 5일에 결제를 했고 구독자 B는 3월 11일에 결제를 했다고 한다면 구독자 A는 변경되기 전 금액인 5,000원이 결제되고 구독자 B는 변경된 금액인 10,000원이 결제가 됩니다.\
\
이후 4월 5일 구독자 A의 정기 결제일이 돌아왔을 때, 결제되는 금액은 3월 10일에 변경된 구독료 10,000원이 아닌 3월 5일에 구독자 A가 처음 결제했던 금액인 5,000원으로 결제됩니다. 구독자 A가 구독을 취소하고 다시 결제하지 않는 이상 계속해서 구독자 A는 5,000원으로 유료 구독을 이용할 수 있습니다.\
\
따라서 이 기능을 사용하면 일정 기간 동안 구독 신청한 구독자에게는 계속해서 할인 혜택을 제공하는 것이 가능합니다.\
\
아래 시나리오는 구독료 변경 기능을 사용해 일정 기간 동안 구독 신청한 구독자에게만 할인 혜택을 적용할 수 있는 방법입니다.

&#x20;

#### **조건**

* 3월 10일에 유료 구독을 정식 런칭할 예정
* 정식 런칭에 앞서 더 많은 구독자를 모으기 위해 3월 1일 \~ 3월 9일까지 신청한 고객들은 평생 50% 할인된 금액(5,000원)으로 구독할 수 있는 프로모션을 진행하고 싶은 상황
* 3월 10일 이후부터 결제하는 구독자들은 모두 정상 가격(10,000원)으로 결제가 이루어져야 함

#### **운영 시나리오**

1. 3월 1일:에 유료 구독 주소록을 만들고 월간 구독료를 5,000원으로 설정함.
2. 3월 1일 \~ 3월 9일: 사전 신청을 접수 받음
3. 3월 10일 00시: 에 월간 구독료를 정상 가격인 10,000원으로 변경함
4. 4월 1일 \~ 4월 9일: 사전 신청한 구독자의 1차 정기 결제 진행됨 (구독료: 5,000원)
5. 4월 10일 \~ 4월 30일: 사전 신청 기간 이후 결제한 구독자의 1차 정기 결제 진행(구독료: 10,000원)
6. 매월 1일 \~ 9일: 사전 신청한 구독자의 N차 정기 결제가 매월 이루어짐 (구독료: 5,000원)
7. 매월 10일 \~ 매월 말일: 사전 신청 기간 이후 결제한 구독자의 N차 정기 결제가 매월 이루어짐 (구독료: 10,000원)

&#x20;

### 주의사항 <a href="#h_4fca3a5450" id="h_4fca3a5450"></a>

구독료가 변경되기 전 구독 신청한 구독자가 '[수신거부](https://help.stibee.com/hc/ko/articles/4756468563983)' 혹은 '[정기 결제를 해지](https://help.stibee.com/hc/ko/articles/4756491765775)'한 후에 다시 결제를 진행하는 경우에는 변경된 금액으로 결제가 진행됩니다. 구독료를 변경한 이후에 이전 금액으로 구독자의 구독료를 변경할 수 없으니 이 점은 유의해주세요.