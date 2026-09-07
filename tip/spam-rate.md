---
layout:
  width: default
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
  metadata:
    visible: true
  tags:
    visible: true
  actions:
    visible: true
---

# 스팸 분류 비율 확인하기

## 언제 필요한가요?

* 이메일이 스팸함으로 분류되는 것 같을 때
* 오픈율이 갑자기 떨어졌을 때
* 구독자 목록을 정리한 뒤 개선 효과를 확인하고 싶을 때

***

## 시작하기 전에 <a href="#h_01hj5kbknvjwezpdv3mw2fk6sx" id="h_01hj5kbknvjwezpdv3mw2fk6sx"></a>

구글 포스트마스터(Postmaster Tools)로 스팸 분류 비율을 확인하려면 발신자 주소의 도메인에 설정을 추가해야 합니다. 설정은 직접 소유하고 있는 도메인에만 설정할 수 있어, gmail.com, naver.com처럼 소유하지 않은 공개된 도메인에는 설정할 수 없습니다.

도메인을 구매하는 방법은 [나만의 발신자 주소를 만들고 싶어요](https://help.stibee.com/getting-started/preparing-for-start/custom-sender-address) 도움말을 참고해 주세요.



## 포스트마스터 툴 설정하기 <a href="#h_01hj5hcj4j9zsvw0srntx0n79e" id="h_01hj5hcj4j9zsvw0srntx0n79e"></a>

{% hint style="info" %}
포스트마스터는 2026년에 새로운 버전으로 바뀌었습니다. 이 도움말은 새로운 버전 화면을 기준으로 안내합니다.
{% endhint %}

포스트마스터는 구글이 제공하는 도구로, 내가 보낸 이메일의 스팸 신고 비율과 발신자 인증 상태, 전달 오류 등을 확인할 수 있습니다. 이 정보를 확인하면 내 이메일이 G메일에서 어떻게 처리되고 있는지 알고 개선할 수 있습니다.

아래 도움말을 따라 설정해도 좋지만, 구글의 공식 가이드를 참고해도 좋습니다. 공식 가이드는 [Postmaster Tools 시작하기](https://support.google.com/mail/answer/9981691?hl=ko) 링크에서 확인할 수 있습니다.



### 설정 시작하기

구글 포스트마스터에 접속해 구글 계정으로 로그인합니다.

* 접속 링크: [https://postmaster.google.com/v2/manage\_domains](https://postmaster.google.com/v2/manage_domains)

로그인한 뒤 화면에 있는 \[새 도메인 추가(Add new domain)] 버튼을 클릭해 도메인 입력 창으로 이동합니다.

<figure><img src="../.gitbook/assets/구글 포스트마스터 v2 1.png" alt=""><figcaption></figcaption></figure>



### 도메인 입력하기 <a href="#h_01hj5j9a87x0vxcd0pmv0eaamg" id="h_01hj5j9a87x0vxcd0pmv0eaamg"></a>

발신자 이메일 주소의 도메인을 입력합니다. 예를 들어 dooly@example.com을 발신자 주소로 사용하고 있다면 도메인은 example.com입니다. 도메인을 입력하고 \[만들기]를 클릭합니다.

**\*주의:** 포스트마스터는 직접 소유한 도메인에만 설정할 수 있습니다. gmail.com, naver.com처럼 소유하지 않은 도메인에는 설정할 수 없습니다.

<figure><img src="../.gitbook/assets/구글 포스트마스터 v2 2.png" alt=""><figcaption></figcaption></figure>



### 도메인 인증하기 <a href="#h_01hj5jckgq3se3tn2b9eas04qq" id="h_01hj5jckgq3se3tn2b9eas04qq"></a>

도메인 인증은 내가 그 도메인의 소유자임을 구글에 확인시키는 단계입니다. 인증을 마치기 전에는 포스트마스터에 이메일 정보가 표시되지 않습니다.

인증에 사용하는 레코드는 도메인을 관리하는 서비스(네임서버가 등록된 곳)에서 추가합니다. 포스트마스터 화면과 도메인 관리 화면을 함께 봐야 하므로, 도메인 관리 서비스는 다른 탭에서 열어두시는 것이 편합니다.

1. 도메인을 등록한 뒤, 다시 한번 \[도메인 관리(Manage Domains)] 페이지에 접속합니다.
2. 인증할 도메인 오른쪽의 \[옵션 더 보기]를 클릭합니다.
3. \[도메인 확인(Verify domain)]을 클릭합니다.
4. '도메인 소유권 확인' 창에서 TXT 또는 CNAME 레코드를 복사합니다.
5. 도메인 관리 서비스에 로그인해 복사한 값을 DNS 레코드에 추가합니다.
6. 포스트마스터의 '도메인 소유권 확인' 창으로 돌아와 \[확인(Verify)]을 클릭합니다.

인증은 보통 바로 완료되지만, 상태가 바뀌기까지 최대 10분이 걸릴 수 있습니다.

<figure><img src="../.gitbook/assets/구글 포스트마스터 v2 3.png" alt=""><figcaption></figcaption></figure>

<figure><img src="../.gitbook/assets/구글 포스트마스터 v2 4.png" alt=""><figcaption></figcaption></figure>



#### 네임서버가 등록된 곳 확인하기

일반적으로 네임서버가 등록된 곳은 처음 도메인을 구한 업체입니다. 정확한 위치는 도메인을 구한 업체의 고객센터에 문의하면 안내받을 수 있습니다.

_\* 네임서버가 등록된 곳이 헷갈린다면_ [_후이즈 도메인 조회_](https://xn--c79as89aj0e29b77z.xn--3e0b707e/kor/whois/whois.jsp)_에서 확인할 수 있습니다. 검색창에 도메인을 입력하고 결과에서 'name server' 항목에 표시된 값이 내 도메인의 네임서버입니다._

네임서버를 확인했다면 'DNS 관리' 화면으로 이동해 레코드를 추가합니다. TXT 레코드를 추가하는 경우 아래 도움말을 참고해 주세요. 다른 서비스 업체를 사용하고 있다면 각 업체의 고객센터로 문의해 주세요.

* 카페24 - [카페24 구매한 도메인을 타 호스팅, 메일에 연결하고 싶어요.](https://help.cafe24.com/cs/cs_faq_view.php?idx=3766) 5) TXT 관리
* 가비아 - [DNS 레코드 설정하기](https://customer.gabia.com/manual#/domain/287/1201) 4) TXT 레코드 설정하기 (SPF 레코드)
* 후이즈 - [SPF(TXT) 값은 어떻게 설정하나요?](http://cs.whois.co.kr/faq/?p=list\&service=1\&category=\&keyfield=subject\&keyword=SPF)

도메인 설정을 직접 진행하기 어려운 상황이라면, 내부 도메인 또는 서버 관리자에게 화면에 표시된 값과 이 도움말의 링크를 함께 전달해 레코드 추가를 요청해 주세요.

{% hint style="info" %}
인증을 눌렀는데 완료되지 않는다면 아래 순서로 확인해 보세요.

* 몇 분 기다린 뒤 다시 시도합니다. 레코드 변경 내용이 구글에 전달되는 데 시간이 걸립니다.
* DNS 레코드에 입력한 값이 포스트마스터 화면의 값과 정확히 같은지 확인합니다.
* 그래도 완료되지 않으면 포스트마스터에서 새 값을 받아 다시 시도합니다.
{% endhint %}



## 스팸 비율 확인하기 <a href="#id-01hj5k6chp47fbvqbs4aqkd5c6" id="id-01hj5k6chp47fbvqbs4aqkd5c6"></a>

{% hint style="info" %}
포스트마스터의 데이터는 개인 G메일 계정으로 보낸 이메일에만 적용됩니다. 개인 G메일 계정은 주소가 gmail.com 또는 googlemail.com으로 끝나는 계정입니다.
{% endhint %}

인증이 완료되면 왼쪽의 \[Spam] 메뉴를 누른 뒤, 도메인을 선택하면 내가 보낸 이메일이 얼마나 스팸으로 신고되는지 확인할 수 있습니다.

G메일에서는 두 가지 기준을 안내합니다.

* 0.3% 미만: 반드시 지켜야 하는 기준입니다. 2024년 2월 1일부터 G메일에 이메일을 보내는 모든 발신자에게 적용됩니다.
* 0.1% 미만: 구글이 권하는 수준입니다. 평소 이 아래로 유지하면 일시적으로 신고가 늘어도 영향을 덜 받습니다.

스팸 신고 비율이 낮아져도 스팸 분류가 바로 개선되지는 않습니다. 구독자 목록을 정리하거나 콘텐츠를 개선한 뒤에는 시간을 두고 비율 변화를 확인해 주세요. 정확한 기준은 구글의 [이메일 발신자 가이드라인](https://support.google.com/mail/answer/81126?hl=ko)에서 확인할 수 있습니다.

<figure><img src="../.gitbook/assets/image (34) (1).png" alt=""><figcaption></figcaption></figure>
