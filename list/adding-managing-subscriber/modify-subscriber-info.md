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

# 구독자 정보 수정하기

### 이 글에서는

구독자 정보를 '개별' 또는 '한 번에 대량으로' 수정하는 방법과 구독자의 '[구독 상태](understanding-subscriber-status.md)'를 변경하는 방법을 알아봅니다.

***

## 구독자 정보 수정하기 <a href="#h_01gfaz0x3r52ctx34kb2155wt1" id="h_01gfaz0x3r52ctx34kb2155wt1"></a>

### 개별로 수정하기 <a href="#h_01gfaz12wkm83w8pzgwk51f3vg" id="h_01gfaz12wkm83w8pzgwk51f3vg"></a>

1. \[주소록 → 구독자 목록]에서 정보를 수정하고 싶은 구독자의 \[이메일 주소]를 클릭하면 \[구독자 대시보드]로 이동합니다.
2. 구독자 이메일 주소 옆에 있는 \[수정하기]버튼을 클릭합니다.
3. 원하는 정보를 수정한 뒤 \[저장하기]를 클릭합니다.

![](<../../.gitbook/assets/1 (7).png>)

![](<../../.gitbook/assets/2 (5).png>)

### 한 번에 대량으로 수정하기 <a href="#h_01gfaz18czypn3dgcj39snsekj" id="h_01gfaz18czypn3dgcj39snsekj"></a>

\[파일로 추가하기]기능을 사용하여 한 번에 여러 구독자 정보를 업데이트할 수 있습니다.

1. 구독자 목록에서 \[필터], \[검색] 기능을 사용하여 정보를 변경하고 싶은 구독자를 조회합니다.
2. 목록 오른쪽 끝부분에 있는 \[내보내기(∨) → 파일로 내보내기]를 클릭하여 구독자 목록을 CSV 파일로 내려받습니다.
3. 내려받은 파일에서 구독자 정보를 수정하고 저장합니다.
4. \[주소록 → 구독자 목록 → + 추가하기 → 파일로 추가하기]를 클릭하여 수정한 파일을 업로드합니다.&#x20;
5. 업로드가 완료되면 추가 결과를 확인합니다.&#x20;

주소록에 이미 존재하는 구독자를 새로 추가한 경우 추가 결과는 '[상태 외 정보 업데이트](https://help.stibee.com/list/adding-managing-subscriber/add#results-of-adding)' 로 기록되며 이메일 주소를 제외한 나머지 정보(예: 이름, 연락처 등)가 최근에 추가한 파일을 기준으로 업데이트됩니다.

<figure><img src="../../.gitbook/assets/3 (6).png" alt=""><figcaption></figcaption></figure>

### 구독자가 직접 변경하기 <a href="#self-serve" id="self-serve"></a>

\[구독 정보 변경 화면]에서 구독자가 자신의 구독 정보를 직접 변경할 수 있습니다. 구독 폼의 구독 확인 메시지나 구독 확인 화면 등의 링크를 통해서 구독자가 구독 정보 변경 화면에 접근할 수 있습니다. \[주소록 - 구독 관리 화면 - 구독 정보 변경 화면]에서 URL을 확인할 수 있습니다.

<figure><img src="../../.gitbook/assets/16.png" alt=""><figcaption></figcaption></figure>

아래 방법으로 URL을 직접 확인할 수도 있습니다. 구독 정보 변경 화면은 아래와 같은 형식으로 구성된 URL로 접근할 수 있습니다.

```
https://page.stibee.com/subscribers/auth/{listid}
```

listid(주소록에 할당된 고유의 아이디)는 아래의 방법으로 확인할 수 있습니다.

* 주소록 목록에서 주소록 이름을 클릭하여 \[주소록 대시보드]로 이동
* 브라우저에 표시되는 URL에서 "lists" 뒤의 숫자를 확인

<figure><img src="../../.gitbook/assets/17 (1).png" alt=""><figcaption></figcaption></figure>

구독 정보 변경 화면의 양식 URL의 {list id] 부분에 확인한 listid 번호를 넣어주고 이 URL로 접속하면 이메일 주소를 입력하는 화면이 표시됩니다.

```
예) https://page.stibee.com/subscribers/auth/3
```

#### 구독 정보 변경 화면 접속하기

확인한 구독 정보 변경 화면의 URL을 구독자가 클릭하면 '이메일 주소' 입력화면으로 이동합니다. 여기에 구독 신청한 이메일 주소를 입력하고 \[구독 정보 변경 링크 보내기]를 클릭하면, 입력한 이메일 주소로 구독 변경 링크가 포함된 이메일이 발송됩니다.

<figure><img src="../../.gitbook/assets/18 (1).png" alt=""><figcaption></figcaption></figure>

\
전송 된 이메일 본문에서 \[네, 이메일 주소가 맞습니다]를 클릭하면, 구독 정보를 변경할 수 있는 화면으로 이동합니다.

<figure><img src="../../.gitbook/assets/19.png" alt=""><figcaption></figcaption></figure>

이 화면에서 이메일 주소, 이름 등 구독 정보가 표시되는 영역 오른쪽의 변경하기를 클릭하면 구독 정보를 변경할 수 있습니다. 수신거부를 클릭하면 수신거부를 할 수 있습니다.

<figure><img src="../../.gitbook/assets/15 (3).png" alt=""><figcaption></figcaption></figure>

### 구독 상태 변경하기 <a href="#h_01gfaz1dqx7jfb1mr5w6myba1t" id="h_01gfaz1dqx7jfb1mr5w6myba1t"></a>

#### 구독 중 ↔ 수신거부 상태 변경하기 <a href="#h_01gfaz1nky8dcanqfs164pz3gk" id="h_01gfaz1nky8dcanqfs164pz3gk"></a>

1. \[주소록 → 구독자 목록]에서 구독 상태를 변경하고 싶은 구독자를 선택합니다.
2. 목록 오른쪽 부분에 있는 \[상태 변경하기 (∨)]를 클릭합니다.
3. 선택한 구독자의 상태에 따라 \[수신거부로 변경하기] 또는 \[수신거부 취소하기]가 표시됩니다. 클릭하면 구독자의 상태가 변경됩니다.

<figure><img src="../../.gitbook/assets/4 (4).png" alt=""><figcaption></figcaption></figure>

\[구독자 목록]뿐 아니라 \[구독자 대시보드]에서도 구독 상태를 변경할 수 있습니다.&#x20;

1. \[주소록 → 구독자 목록 → 구독자 이메일 주소]를 클릭하여 \[구독자 대시보드]로 이동합니다.
2. 구독자 이메일 주소 옆부분에 구독자의 상태에 따라 \[수신거부 하기] 또는 \[수신거부 취소하기]가 표시됩니다.
3. 버튼을 클릭하여 구독자의 구독 상태를 변경합니다.

![](<../../.gitbook/assets/5 (5).png>)

#### 한번에 여러 구독자를 수신거부로 변경하기

한번에 20명 이상 구독자를 수신거부 상태로 변경하려면 \[파일로 추가하기] 기능을 활용하면 됩니다. CSV 파일에서 수신거부 여부를 표시할 열을 추가합니다. 수신거부 상태로 추가할 구독자는 이 열에 **Y**를 입력합니다.&#x20;

구독자 정보가 주소록의 어떤 항목에 해당하는지 선택할 때, 수신거부에 대한 값을 입력한 열을 **수신거부** 항목으로 선택합니다.&#x20;

<figure><img src="../../.gitbook/assets/12 (1).png" alt=""><figcaption></figcaption></figure>

수신거부 항목으로 선택된 열에 **Y**가 입력되어있으면, 그 구독자는 수신거부 상태로 추가됩니다. 만약 이미 등록된 구독자라면, 수신거부 상태로 변경됩니다.

<figure><img src="../../.gitbook/assets/13.png" alt=""><figcaption></figcaption></figure>

#### '자동삭제' → '구독 중' 상태 변경하기 <a href="#h_01gfaz1x2me72n38hnadrrr4r8" id="h_01gfaz1x2me72n38hnadrrr4r8"></a>

1. 목록에서 \[구독 중(∨) → 자동삭제 → 적용하기]를 클릭하여 구독 상태가 ‘자동삭제’인 구독자를 검색합니다.
2. '구독 중'으로 변경하고 싶은 구독자를 선택하고 목록 오른쪽 윗부분의 \[상태 변경하기(∨) → 자동삭제 취소하기]를 클릭합니다.

![](<../../.gitbook/assets/6 (5).png>)

\[구독자 대시보드]에서 구독 상태를 변경하는 것도 가능합니다.

1. \[주소록 → 구독자 목록 → 구독자 이메일 주소]를 클릭하여 \[구독자 대시보드]로 이동합니다.
2. 구독자 이메일 주소 옆부분에 있는 \[자동삭제 취소하기]를 클릭합니다.
3. 구독자의 상태가 \[구독 중]으로 변경됩니다.

![](<../../.gitbook/assets/7 (4).png>)

\[자동 삭제]로 처리된 구독자는 하드바운스로 발송에 실패한 구독자이기 때문에 다시 이메일을 발송한다고 해도 이메일이 발송되지 않을 확률이 높습니다. 자동 삭제로 처리된 구독자의 구독 상태는 가능하면 변경하지 않는 것을 권장합니다.



## 구독자 삭제하기 <a href="#h_01gfaz23xcpzghh2cbps07sm97" id="h_01gfaz23xcpzghh2cbps07sm97"></a>

{% hint style="info" %}
구독자를 삭제하는 경우 관련 통계, 활동 기록이 모두 함께 삭제됩니다. 삭제된 정보는 복구 할 수 없습니다. 이메일이 발송된 상태에서 구독자 정보를 삭제하는 경우 이메일 통계 기록에 문제가 있을 수 있습니다.
{% endhint %}

### **한번에 여러 구독자 삭제하기**

1. \[주소록 → 구독자 목록]에서 삭제하고 싶은 구독자를 선택합니다.
2. 목록 오른쪽 윗부분 \[상태 변경하기(∨) → 완전 삭제하기]를 클릭하여 \[구독자 정보 삭제] 화면으로 이동합니다.
3. \[구독자 정보 삭제] 화면에 선택한 구독자 정보가 자동으로 등록되어 있습니다. 추가로 삭제하고 싶은 구독자가 있다면 줄 바꿈으로 여러 개의 이메일 주소를 추가합니다.
4. 삭제하고 싶은 구독자를 모두 추가했다면 \[완전 삭제하기]를 클릭하여 구독자를 삭제합니다.

![](<../../.gitbook/assets/8 (6).png>)

<figure><img src="../../.gitbook/assets/9 (7).png" alt=""><figcaption></figcaption></figure>

### 구독자 한명씩 삭제하기

1. \[주소록 → 구독자 목록 → 구독자 이메일 주소]를 클릭하여 삭제하고 싶은 구독자의 \[구독자 대시보드]로 이동합니다.
2. 구독자 이메일 주소 옆 \[완전 삭제하기]버튼을 클릭합니다.
3. 확인창에서 \[예]를 클릭하여 구독자 정보를 삭제합니다.

![](<../../.gitbook/assets/10 (3).png>)

## 광고성 정보 수신 동의 여부 변경하기 <a href="#change-promotional-consent" id="change-promotional-consent"></a>

관리자가 구독자를 신규로 '직접 추가'하거나 '파일로 추가'할 때, 광고성 정보 수신 동의 여부를 선택할 수 있으며, 주소록에 이미 추가되어 있는 구독자의 광고성 정보 수신 동의 여부를 한 명씩 혹은 여러 명을 한꺼번에 변경할 수 있습니다.\


### 관리자가 변경하기

#### 한명씩 변경하기

구독자 대시보드에서 각 구독자의 광고성 정보 수신 동의 여부를 변경할 수 있습니다. \[주소록 → 구독자 목록]에서 광고성 정보 수신 동의 여부 수정이 필요한 구독자를 클릭해서 구독자 대시보드로 이동하고 \[수정하기]를 클릭합니다.

<figure><img src="../../.gitbook/assets/11 (3).png" alt=""><figcaption></figcaption></figure>

\
구독자 정보 수정 화면에서 광고성 정보 수신 동의 여부를 변경한 후 \[저장하기] 버튼을 클릭합니다.

<figure><img src="../../.gitbook/assets/12 (2).png" alt=""><figcaption></figcaption></figure>

#### 한번에 여러 명 변경하기

이미 주소록에 추가되어 있는 구독자 여러 명의 광고성 정보 수신 동의 여부를 한 번에 변경하기 위해서는 \[파일로 추가하기]로 '[상태 외 정보 업데이트](https://help.stibee.com/list/adding-managing-subscriber/add#results-of-adding)'를 진행해야 합니다. 파일로 추가하기 기능을 통해 광고성 정보 수신 동의 여부를 선택하기 위해서는 광고성 정보 수신 여부를 '동의'로 변경해야 하는 구독자는 파일에 미리 '광고성 정보 수신 동의' 열을 만들어 'Y'를 입력해야 합니다. \[주소록 → 추가하기 → 파일로 추가하기]를 클릭해 파일을 업로드합니다.

<figure><img src="../../.gitbook/assets/13 (1).png" alt=""><figcaption></figcaption></figure>

구독자 파일 업로드 후 필드 선택 단계에서 광고성 정보 수신 동의 여부가 체크되어 있는 열에 '광고성 정보 수신 동의' 필드를 선택합니다. Y가 입력된 구독자는 광고성 정보 수신 동의 여부가 '동의'로 변경됩니다. N으로 입력된 구독자는 광고성 정보 수신 동의 여부가 '동의하지 않음(빈칸)'으로 표시됩니다.

<figure><img src="../../.gitbook/assets/14 (2).png" alt=""><figcaption></figcaption></figure>

### 구독자가 직접 변경하기

구독 정보 변경 화면에서 \[광고성 정보 수신 동의] 항목의 \[변경하기]를 클릭해 구독자가 직접 자신의 광고성 정보 수신 동의 여부를 수정할 수 있습니다. 구독자가 직접 정보를 변경 하는 방법에 대한 자세한 내용은 [여기](modify-subscriber-info.md#h\_01gfaz1dqx7jfb1mr5w6myba1t)[ ](modify-subscriber-info.md#self-serve)링크에서 확인해보세요.

<figure><img src="../../.gitbook/assets/15 (2).png" alt=""><figcaption></figcaption></figure>

