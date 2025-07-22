# HTML 코드로 편집하기

## 이 글에서는 <a href="#h_183ecaf6df" id="h_183ecaf6df"></a>

스티비 에디터를 사용하면 별다른 HTML 코드 편집 없이도 이메일을 만들어 보낼 수 있습니다. 그러나 필요하다면 HTML 코드로 이메일 전체를 편집하거나 일부분만 편집해서 보내는 것도 가능합니다. 그 사용법에 대해서 알아봅니다.

***

## 이메일 전체를 HTML로 편집하기 <a href="#h_183ecaf6df" id="h_183ecaf6df"></a>

{% hint style="info" %}
이메일 환경은 일반적인 웹 환경과 다르기 때문에 HTML 코드를 작성할 때 몇 가지 주의해야 할 점이 있습니다. 자세한 내용은 [HTML 상자를 사용할 때 기억할 다섯 가지!](https://blog.stibee.com/html-%EC%83%81%EC%9E%90%EB%A5%BC-%EC%82%AC%EC%9A%A9%ED%95%A0-%EB%95%8C-%EA%B8%B0%EC%96%B5%ED%95%A0-%EB%8B%A4%EC%84%AF-%EA%B0%80%EC%A7%80-64a5530761e4) 블로그 글을 참고하세요.
{% endhint %}

이메일 본문 전체를 HTML로 편집할 수도 있습니다. \[템플릿] 단계에서 \[HTML 에디터로 만들기]를 선택하면 이메일을 HTML 코드로 편집할 수 있는 화면이 표시됩니다. 왼쪽의 HTML 코드 입력창에 코드를 입력하면 오른쪽에서 실시간으로 작업 내용을 확인할 수 있습니다.&#x20;

**\*주의:** HTML 로 편집할 때 아래 태그는 사용이 불가능합니다. (Script 실행 코드도 사용할 수 없습니다.)

{% code overflow="wrap" %}
```
<script>, <head>, <body>, <html>, <style>, <form>, <input>, 
<button>, <noscript>, <meta>, <iframe>
```
{% endcode %}

<figure><img src="../../.gitbook/assets/HTML 템플릿으로 편집하기.gif" alt=""><figcaption></figcaption></figure>



HTML로 편집할 때도 스티비를 사용해 이메일을 발송한다면 \[웹에서 보기], \[수신거부] 등의 기능도 사용하는 것이 가능합니다. 아래 예시를 참고하세요.

* _웹에서보기_
  * ```
    <a href="$%permalink%$">웹에서 보기</a>
    ```
* 수신거부
  * ```
    <a href="$%unsubscribe%$">수신거부</a>
    ```



## HTML에서 메일머지 기능 사용하기

HTML 코드에서도 메일머지 기능을 사용할 수 있습니다. \[[사용자 정의 필드](../../list/adding-managing-subscriber/understanding-subscriber-info.md)]의 Key값을 입력하면 구독자마다 개인화 된 메시지(예. 구독자 이름, 쿠폰 번호 등)를 발송할 수 있습니다. 태그는 $%key%$의 형식으로 입력하면 됩니다.

기본으로 제공되는 사용자 정의 필드의 Key 값은 다음과 같습니다.

* $%email%$: 구독자의 이메일 주소
* $%name%$: 구독자의 이름

이 외에도 다른 필드를 직접 추가할 수 있습니다. 사용자 정의 필드를 추가하는 방법은 [구독자 정보 이해하기](../../list/adding-managing-subscriber/understanding-subscriber-info.md) 참고해 주세요.



## HTML에서 수신거부 기능 사용하기 <a href="#unsubscribe" id="unsubscribe"></a>

\[HTML로 직접 만들기] 또는 \[HTML 상자] 템플릿을 사용하는 경우 수신거부 치환자를 링크로 직접 입력하면 됩니다.  예를 들어 "수신거부"라는 텍스트에 수신거부 링크를 넣는다면 아래와 같이 넣어주면 됩니다. 텍스트 뿐만 아니라 이미지 등 다른 요소에도 동일하게 링크를 넣으면 됩니다.

```
<a href="$%unsubscribe%$">수신거부</a>
```

이렇게 추가한 수신거부 링크는 이메일을 발송할 때 구독자마다의 고유한 값으로 변환됩니다. 수신거부 기능은 이메일이 실제로 발송 된 경우에만 작동하며 '테스트 발송하기'로 발송한 이메일에서는 작동 하지 않습니다.



## HTML 에서 미리보기 텍스트 사용하기 <a href="#preview-text" id="preview-text"></a>

\[HTML로 만들기 템플릿]에서는 발송정보의 미리보기 텍스트는 비활성화됩니다. HTML 템플릿에서도 미리보기 텍스트를 사용하려면 별도의 HTML 코드를 직접 입력해야 합니다. 아래 예제를 참고하여 미리보기 텍스트 HTML 코드를 작성합니다. "여기에 미리보기 텍스트를 입력하세요."를 미리보기 텍스트 내용으로 수정합니다. 줄바꿈 없이 이어서 작성하는 것이 좋습니다.&#x20;

예제)

{% code overflow="wrap" %}
```html
<table id="$stb-htmlv3$" style="height: 0px; max-height: 0px; border-width: 0px; border-color: initial; border-image: initial; visibility: hidden; line-height: 0px; font-size: 0px; overflow: hidden;display:none;">
<tr><td>미리보기 텍스트를 입력하세요.</td></tr></table>
```
{% endcode %}

작성한 코드를 이메일 콘텐츠 HTML 코드에 붙여 넣습니다. 태그가 있는 경우 태그 바로 아래에 붙여 넣습니다. 태그가 없는 경우 HTML 코드의 가장 상단에 붙여 넣습니다. 이렇게 입력한 내용은, 이메일 콘텐츠에는 표시되지 않고 받은 편지함의 미리보기 텍스트 영역에 표시됩니다.



## 이메일의 일부만 HTML 코드로 편집하기

💬 이내용은 **스탠다드, 프로, 엔터프라이즈 요금제**에 해당하는 도움말입니다.

***

HTML 코드 상자를 사용하면 본문 중 일부만 HTML 코드로 편집할 수 있습니다. HTML 코드 상자는 스탠다드 요금제부터 사용 가능합니다. 에디터에서 HTML 코드로 작성한 내용을 바로 확인 할 수 있습니다. 오른쪽 패널에서는 HTML 코드를 직접 입력하고 수정할 수 있습니다.&#x20;

HTML 코드 상자에서도 전체 이메일 템플릿과 마찬가지로 아래 태그는 사용이 불가능합니다. Script 실행 코드도 사용이 불가능합니다.

```
<script>, <head>, <body>, <html>, <style>, <form>, <input>, 
<button>, <noscript>, <meta>, <iframe>
```

![](https://downloads.intercomcdn.com/i/o/400649040/dde7e3458f10d02047990535/ezgif.com-gif-maker+\(19\).gif)
