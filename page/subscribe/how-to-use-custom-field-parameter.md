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

# 페이지 URL 사용자 정의 필드 파라미터 사용하기

## 이 글에서는

페이지 URL 뒤에 사용자 정의 필드 키값을 파라미터로 추가하면 구독자 정보를 자동으로 추가할 수 있습니다. 이 방법에 관해 알아봅니다.

***

## 파라미터 이해하기 <a href="#h_9840f80d07" id="h_9840f80d07"></a>

파라미터란, URL에 특정한 형식을 넣어 값이 미리 적용될 수 있도록 하는 기능을 의미합니다. 파라미터가 없는 경우에는 값이 빈 상태로 보이며, 파라미터가 있다면 값이 미리 등록됩니다. 단, 파라미터를 활용해서 특정 구독자 정보가 미리 입력되어 있어도 구독자가 입력된 값을 수정하면 수정한 값이 저장됩니다.

사용자 정의 필드 URL 파라미터를 사용하면 [추천인 기능](https://help.stibee.com/hc/ko/articles/4971631583119)을 구현할 수 있습니다. 이 외에도 다양한 정보를 수집하는 데 활용할 수 있습니다.

#### 페이지 URL 사용자 정의 필드 형식 이해하기

페이지 구독 폼 URL에 이름 필드(name)를 파라미터로 미리 입력했을 때와 입력하지 않았을 때의 차이를 아래 이미지를 통해서 확인할 수 있습니다.

* 파라미터가 적용되지 않은 페이지 URL: https://{subdomain}.stibee.com
  * 별도의 정보 입력되지 않음
* 파라미터가 적용된 페이지 URL:  https://{subdomain}.stibee.co&#x6D;**?name=스티비**
  * '이름' 필드에 '스티비'가 미리 입력되어 있음

<figure><img src="https://downloads.intercomcdn.com/i/o/528916728/c5df1c069d7c9bfffede6c13/%ED%8E%98%EC%9D%B4%EC%A7%80%EC%82%AC%EC%9A%A9%EC%9E%90%EC%A0%95%EC%9D%98%ED%95%84%EB%93%9C%ED%8C%8C%EB%9D%BC%EB%AF%B8%ED%84%B0_2.gif" alt=""><figcaption></figcaption></figure>

사용자 정의 필드 파라미터가 아닌, 특정 그룹에 분류되도록 하는 그룹 파라미터 기능도 사용할 수 있습니다. 자세한 내용은 [how-to-use-group-parameter.md](how-to-use-group-parameter.md "mention") 도움말을 참고해 주세요.



## 페이지 URL 사용자 정의 필드 파라미터 사용하기 <a href="#h_b4c1c49ce3" id="h_b4c1c49ce3"></a>

페이지 URL은 아래의 형식으로 만들어집니다.

* 형식: https://{subdomain}.stibee.com
* 예: https://newsletter.stibee.com

이 URL 뒤에 아래 형식으로 '사용자 정의 필드의 키 값'을 추가하면 구독자가 구독을 신청할 때 자동으로 구독자 정보에 특정 값이 입력됩니다.

* 형식: https://{subdomain}.stibee.co&#x6D;**?field\_key={field\_value}**
* 예: https://newsletter.stibee.co&#x6D;**?route=stibee**

'field\_key'는 사용자 정의 필드의 키 값입니다. \[주소록 → 사용자 정의 필드]에서 키(key) 값을 확인해 주세요.

<figure><img src="https://downloads.intercomcdn.com/i/o/528908888/5134a4728a731241b7fd2c2b/%EC%82%AC%EC%9A%A9%EC%9E%90%EC%A0%95%EC%9D%98%ED%95%84%EB%93%9C%ED%8C%8C%EB%9D%BC%EB%AF%B8%ED%84%B0_3.gif" alt=""><figcaption></figcaption></figure>

## 주의사항

* 사용자 정의 필드에 없는 필드를 파라미터로 넣는 경우 정보가 입력되지 않습니다.
* 페이지의 구독 폼에서 파라미터로 설정한 필드의 값을 구독자가 변경하는 경우 변경된 값으로 정보가 입력됩니다.
