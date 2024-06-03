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

파라미터란, URL에 특정한 형식을 넣어 미리 값이 적용될 수 있도록 하는 기능을 의미합니다. 파라미터가 없는 경우에는 값이 빈 상태로 보여지며, 파라미터가 있다면 값이 미리 등록됩니다. (파라미터로 값이 미리 등록되어 있어도 값을 바꾸면 바꾼 값으로 저장됩니다.)

페이지 URL 뒤에 사용자 정의 필드 키 값을 파라미터로 추가하면 구독자 정보를 자동으로 추가할 수 있습니다. 이 방법에 관해 알아봅니다.

***

## 파라미터 이해하기 <a href="#h_9840f80d07" id="h_9840f80d07"></a>

페이지 구독 폼 URL에 이름 필드(name)를 파라미터로 미리 입력했을 때와 입력하지 않았을 때의 차이를 아래 이미지를 통해서 확인할 수 있습니다.



### **파라미터가 적용되지 않은 페이지 URL**

* https://{subdomain}.stibee.com (subdomain은 페이지 설정에 따라 달라집니다.)&#x20;

<figure><img src="https://downloads.intercomcdn.com/i/o/528915667/9985ee2c3099df298980205b/%ED%8E%98%EC%9D%B4%EC%A7%80%EC%82%AC%EC%9A%A9%EC%9E%90%EC%A0%95%EC%9D%98%ED%95%84%EB%93%9C%ED%8C%8C%EB%9D%BC%EB%AF%B8%ED%84%B0_1.gif" alt=""><figcaption></figcaption></figure>



### **파라미터가 적용된 페이지 URL**

* https://{subdomain}.qa-page.stibee.com**?name=스티비** (subdomain은 페이지 설정에 따라 달라집니다.)&#x20;

<figure><img src="https://downloads.intercomcdn.com/i/o/528916728/c5df1c069d7c9bfffede6c13/%ED%8E%98%EC%9D%B4%EC%A7%80%EC%82%AC%EC%9A%A9%EC%9E%90%EC%A0%95%EC%9D%98%ED%95%84%EB%93%9C%ED%8C%8C%EB%9D%BC%EB%AF%B8%ED%84%B0_2.gif" alt=""><figcaption></figcaption></figure>

페이지가 아닌 일반 [구독 폼](../../list/gather-subscribers/form.md#h\_01ggcbmn0c7yk62feh8bwj7xg6)에서도 파라미터를 추가해 사용할 수 있습니다. 사용자 정의 필드 URL 파라미터를 사용해 [추천인 기능](https://help.stibee.com/hc/ko/articles/4971631583119)을 구현할 수 있고 이외에도 다양한 정보를 수집할 수 있습니다.\
\
페이지에서도 그룹으로 자동 배정이 되는 그룹 파라미터 기능을 사용할 수 있습니다.\
\
페이지에서 구독 시 그룹으로 자동 분류하고 싶다면 [그룹 파라미터](https://help.stibee.com/hc/ko/articles/4756482888463)를 페이지 URL 뒤에 넣어서 사용하면 됩니다.



## 페이지 URL 사용자 정의 필드 파라미터 사용하기 <a href="#h_b4c1c49ce3" id="h_b4c1c49ce3"></a>

페이지 URL은 아래의 형식으로 생성됩니다.

* https://{subdomain}.stibee.com
* 예. https://syoletter.stibee.com

이 URL 뒤에 아래의 형식으로 "사용자 정의 필드의 키 값"을 추가하면 구독 시 구독자 정보에 원하는 값이 자동으로 입력되도록 설정할 수 있습니다.

* https://{subdomain}.stibee.com**?field\_key={field\_value}**
* 예. https://syoletter.stibee.com?route=stibee

field\_key는 사용자 정의 필드의 키 값으로 주소록 내 사용자 정의 필드에서 확인할 수 있습니다.

&#x20;

<figure><img src="https://downloads.intercomcdn.com/i/o/528908888/5134a4728a731241b7fd2c2b/%EC%82%AC%EC%9A%A9%EC%9E%90%EC%A0%95%EC%9D%98%ED%95%84%EB%93%9C%ED%8C%8C%EB%9D%BC%EB%AF%B8%ED%84%B0_3.gif" alt=""><figcaption></figcaption></figure>



## **주의사항** <a href="#h_e7965db396" id="h_e7965db396"></a>

* 사용자 정의 필드에 없는 필드를 파라미터로 넣는 경우 정보가 입력되지 않습니다.
* 페이지의 구독 폼에서 파라미터로 설정한 필드의 값을 구독자가 변경하는 경우 변경된 값으로 정보가 입력됩니다.
