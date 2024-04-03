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

# 도메인 설정하기

## 이 글에서는

도메인을 구입하고 나만의 발신자 이메일 주소를 만들었다면 이제 도메인에 몇가지 설정을 추가하면 됩니다. 이 도움말에서는 설정을 어디서 추가하면 되는지 알아봅니다.&#x20;

***

## 내 도메인 관리 서비스 확인하기

도메인 설정은 내 도메인을 관리하고 있는 서비스에서 설정해야 합니다. 내 도메인은 '네임서버'가 설치된 곳에서 관리할 수 있습니다.

네임서버는 사람이 인식하는 글자와 컴퓨터가 인식하는 숫자를 인식해 서로 맞는 값으로 바꿔주는 역할을 수행합니다.  사람은 도메인을 글자로 인식하지만 컴퓨터는 글자가 아닌 숫자로 도메인을 인식합니다. 네임서버가 있기 때문에 사람은 도메인을 숫자 형태로 기억하지 않고 이해하기 편한 문자 형태로 입력해 원하는 홈페이지에 접근할 수 있고 컴퓨터는 입력된 정보를 숫자 형태로 변환하여 정확한 홈페이지 주소를 전달할 수 있습니다.

도메인의 네임서버는 보통 도메인을 구입한 곳에 설치됩니다. 다만 종종 도메인을 구입한 곳과 네임서버가 설치된 곳이 다를 수 있습니다. 자세한 내용은 도메인을 구입한 곳의 고객센터를 통해 문의하면 확인할 수 있습니다.

[_후이즈 도메인 조회_](https://xn--c79as89aj0e29b77z.xn--3e0b707e/kor/whois/whois.jsp)_에서 직접 확인하는 것도 가능합니다. 검색창에 도메인을 입력하고 결과에 'name server' 부분에 입력된 링크가 내 도메인의 네임서버가 등록된 곳입니다._



## DNS 설정으로 이동하기

내 도메인의 관리 서비스가 어디인지 확인했다면 사용하고 있는 서비스의 'DNS 설정' 화면으로 이동합니다. 사용하는 서비스에 따라 DNS 설정이 어디에 있는지 여부가 달라지기 때문에 메뉴를 찾는 것이 어렵다면 사용하고 있는 서비스의 고객센터로 "도메인의 DNS 설정을 수정하려면 어디서 수정해야 하는지." 문의하면 정확하게 확인할 수 있습니다.&#x20;



## SPF, DKIM, DMARC 설정하기

DNS 설정 화면으로 이동했다면 다음은 스티비의 SPF, DKIM 값과 DMARC 레코드를 추가하면 됩니다. 자세한 설정 방법은 각각 아래 도움말을확인해보세요.

{% content-ref url="../../email/sender/spf-dkim.md" %}
[spf-dkim.md](../../email/sender/spf-dkim.md)
{% endcontent-ref %}

{% content-ref url="../../email/sender/dmarc.md" %}
[dmarc.md](../../email/sender/dmarc.md)
{% endcontent-ref %}



## 스팸 비율 모니터링하기

[구글 포스트마스터 툴(Postmaster Tools)](https://support.google.com/a/answer/9981691?hl=ko\&ref=help.stibee.com) 사용하면 G메일로 보낸 이메일이 얼마나 스팸으로 분류되는지 비율을 확인할 수 있습니다. G메일에서는 G메일로 발송되는 이메일의 스팸 비율이 0.1% 미만으로 유지할 것을 권장하고 있고 0.3%를 넘으면 안된다고 안내하고 있습니다. 포스트마스터 툴도 마찬가지로 DNS 설정에서 TXT 레코드를 추가하는 방식으로 설정할 수 있습니다. 자세한 설정 방법은 아래 도움말을 확인해보세요.

{% content-ref url="../../email/send/spam-rate.md" %}
[spam-rate.md](../../email/send/spam-rate.md)
{% endcontent-ref %}

