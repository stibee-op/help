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

# 스팸 분류 비율 확인하기

## 이 글에서는 <a href="#h_01hj5kbgtqeb3k8khf3qsfas53" id="h_01hj5kbgtqeb3k8khf3qsfas53"></a>

구글의 Postmaster 도구를 사용해 내가 보낸 이메일이 얼마나 스팸으로 분류되고 있는지 비율을 확인하는 방법에 대해 알아봅니다.

***

## 시작하기 전에 <a href="#h_01hj5kbknvjwezpdv3mw2fk6sx" id="h_01hj5kbknvjwezpdv3mw2fk6sx"></a>

구글 포스트마스터 툴(Postmaster Tools)을 활용해 이메일의 스팸 분류 비율을 확인하기 위해서는 발신자 주소의 도메인에 설정을 추가해야 합니다. 설정은 직접 소유하고 있는 도메인에만 설정이 가능하기 때문에 gmail.com, naver.com 등 직접 소유하지 않은 공개된 도메인에는 설정이 불가능합니다.

도메인을 구입하는 방법은 [나만의 발신자 주소를 만들고 싶어요](../../getting-started/preparing-for-start/custom-sender-address.md) 도움말을 참고해 주세요.



## 포스트마스터 툴 설정하기 <a href="#h_01hj5hcj4j9zsvw0srntx0n79e" id="h_01hj5hcj4j9zsvw0srntx0n79e"></a>

구글에서 제공하는 포스트마스터 툴(Postmaster Tools) 도구를 사용하면 내가 보낸 이메일의 스팸 분류 비율, 도메인 평판 등 여러 정보를 확인할 수 있습니다. 이 비율을 확인하면 전반적으로 내가 보낸 이메일이 얼마나 스팸으로 분류되고 있는지 알고 콘텐츠를 개선할 수 있습니다.

아래 도움말을 따라 설정해도 좋지만 구글에서 제공하는 포스트마스터 공식 설정 가이드를 참고해도 좋습니다. 구글의 공식 가이드가 궁금하다면 [Postmaster Tools 시작하기](https://support.google.com/a/answer/9981691?hl=ko\&visit\_id=638409959549630881-476537399\&rd=1) 링크를 클릭하세요.



### 설정 시작하기

[https://postmaster.google.com](https://postmaster.google.com/)를 클릭해 포스트마스터 도구에 로그인합니다. 도구를 사용하기 위해서는 구글 계정이 필요합니다. 로그인을 한 뒤 화면에 있는 \[+] 버튼을 클릭해 도메인 입력 창으로 이동합니다.

<figure><img src="../../.gitbook/assets/image (30) (1).png" alt=""><figcaption></figcaption></figure>

### 도메인 입력하기 <a href="#h_01hj5j9a87x0vxcd0pmv0eaamg" id="h_01hj5j9a87x0vxcd0pmv0eaamg"></a>

발신자 이메일 주소로 사용하고 있는 주소의 도메인을 입력합니다. 예를 들면 dooly@example.com 이라는 발신자 이메일 주소를 사용하고 있다면 이 경우 도메인은 example.com 입니다. 이 도메인을 입력하고 \[NEXT]를 클릭합니다.&#x20;

**\*주의:** 포스트마스터 툴은 직접 소유하고 있는 도메인에만 설정이 가능합니다. gmail.com, naver.com 등 직접 소유하지 않은 공개된 URL에는 설정이 불가능합니다.

<figure><img src="../../.gitbook/assets/image (31) (1).png" alt=""><figcaption></figcaption></figure>

### 도메인 인증하기 <a href="#h_01hj5jckgq3se3tn2b9eas04qq" id="h_01hj5jckgq3se3tn2b9eas04qq"></a>

내 도메인에 TXT 레코드를 추가하면 설정이 마무리됩니다. TXT 레코드는 내 도메인에 직접 해줘야 하는 설정이기 때문에 도메인을 관리하는 서비스(네임서버가 등록된 곳)에서 설정하면 됩니다. 도메인의 네임 서버가 등록된 곳은 상황에 따라 다르지만 보통 처음 도메인을 구입한 곳에 등록되어 있을 확률이 높습니다. 자세한 내용은 도메인을 구입한 곳의 고객센터를 통해 문의해 보시면 안내 받아보실 수 있습니다.&#x20;

_네임서버가 등록된 곳이 어디인지 헷갈린다면_ [_후이즈 도메인 조회_](https://xn--c79as89aj0e29b77z.xn--3e0b707e/kor/whois/whois.jsp)_에서 직접 확인할 수 있습니다. 사이트에 접속한 뒤, 검색창에 URL을 입력하고 결과에 'name server' 부분에 입력된 링크가 내 도메인의 네임서버가 등록된 곳입니다._

<figure><img src="../../.gitbook/assets/image (32) (1).png" alt=""><figcaption></figcaption></figure>



네임서버가 설치된 내 도메인 관리 서비스를 확인했다면 다음은 관리 서비스의 'DNS 관리' 화면으로 이동해 TXT 레코드를 추가 해주면 됩니다. 레코드를 추가할 때 입력하는 값은 포스트마스터 서비스에서 확인한 값을 넣어주면 됩니다.

도메인 관리 서비스마다 경로가 다르지만 일반적으로 "도메인 관리", "DNS 관리" 등의 화면을 찾으시면 됩니다. 아래 서비스를 사용하고 있다면 링크된 각 도움말이나 아래 업체가 아닌 다른 서비스를 사용하고 있다면 그 서비스의 고객센터로 문의하면 자세하게 안내 받아볼 수 있습니다.

* **카페24**\
  \- [카페24 구매한 도메인을 타 호스팅, 메일에 연결하고 싶어요.](https://help.cafe24.com/cs/cs\_faq\_view.php?idx=3766) ⑤ TXT 관리
* **가비아**\
  \- [DNS 레코드 설정하기](https://customer.gabia.com/manual#/domain/287/1201) 4) TXT 레코드 설정하기 (SPF 레코드)
* **후이즈**\
  \- [SPF(TXT) 값은 어떻게 설정하나요?](http://cs.whois.co.kr/faq/?p=list\&service=1\&category=\&keyfield=subject\&keyword=SPF)
* **구글 도메인**\
  \- [리소스 레코드](https://support.google.com/domains/answer/3290350?hl=ko\&ref\_topic=9018335)



도메인의 설정을 직접 수정할 수 없는 경우라면 내부의 도메인 또는 서버 관리자에게 화면에 표시된 값과 이 도움말의 링크를 함께 전달해 TXT 레코드 추가를 요청해 주세요. TXT 레코드가 정상적으로 추가됐다면 도메인 대시보드에서 status의 상태가 verified로 변경됩니다.

설정이 완료되면 내가 보낸 이메일이 얼마나 스팸으로 분류되는지 비율을 확인할 수 있습니다.



## 스팸 비율 확인하기 <a href="#id-01hj5k6chp47fbvqbs4aqkd5c6" id="id-01hj5k6chp47fbvqbs4aqkd5c6"></a>

설정이 완료됐다면 이제 내가 보낸 이메일이 얼마나 스팸으로 분류되는지 비율을 확인할 수 있습니다.&#x20;

<figure><img src="../../.gitbook/assets/image (34) (1).png" alt=""><figcaption></figcaption></figure>
