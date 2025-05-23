# 사용 중 문제가 생겼을 때

## 언제 필요한가요? <a href="#h_01hkm26fsyrr8kbfdtmncznw7h" id="h_01hkm26fsyrr8kbfdtmncznw7h"></a>

* 스티비 서비스 사용 중 문제가 생겼을 때

***

서비스를 이용하다 보면 간혹 사용이 원활하지 않을 때가 있습니다. 예를 들어, 편집 상자가 끌어 당겨지지 않거나, 이메일 편집 시 하단에 공백이 추가되거나, 로그인이 정상적으로 이루어지지 않는 등의 문제가 발생하는 경우가 있습니다. 이러한 문제는 내 사용 환경의 문제인지 스티비의 문제인지 판단하기 어려운 경우가 많습니다.

아래 내용을 참고하여 직접 해결할 수 있는 문제인지 확인하고 해결 방법을 살펴보세요.



## **시크릿 모드에서 확인하기**

시크릿 모드에서도 같은 문제가 발생하는지 확인해 보세요. 시크릿 모드는 아래 방법으로 실행할 수 있습니다.

* 윈도우: Ctrl + Shift + N
* 맥: ⌘ + Shift + N

### 시크릿 모드에서는 정상적으로 동작한다면

시크릿 모드에서는 정상적으로 동작한다면 아래 방법을 순서대로 시도해 보세요.

#### **1. 로컬 스토리지 삭제하기**

브라우저에 데이터가 많이 쌓여 문제가 발생한 상황일 수 있습니다. 아래 방법으로 로컬 스토리지를 삭제해 보실 수 있습니다.

1. 크롬 브라우저에서 F12를 눌러 개발자 콘솔이 표시되게 합니다.
2. 콘솔 상단에 있는 \[application]을 클릭합니다.
3. \[Storage → Local Storage]를 클릭해 메뉴를 펼칩니다.
4. https://editor.stibee.com 또는 https://stibee.com 항목을 선택하고 상단에 있는 금지 표시(🚫)를 클릭해 기록을 삭제합니다.
5. 새로고침 후에 다시 확인합니다.

#### **2. 확장 프로그램 비활성화 하기**

로컬 스토리지를 삭제했으나 계속해서 문제가 발생하는 경우, 브라우저에 설치된 '확장 프로그램'이 문제를 일으키는 상황일 수 있습니다. 다만, 어떤 확장 프로그램이 원인인지는 저희 쪽에서 확인이 어렵습니다.&#x20;

최근에 설치된 순서대로 하나씩 비활성화하며 원인이 되는 확장 프로그램을 확인하시는 방법을 추천드립니다.

설치된 확장 프로그램을 확인하는 방법은 아래 도움말에서 확인할 수 있습니다.

* [Chrome 웹 스토어 고객센터 ](https://support.google.com/chrome_webstore/answer/2664769?hl=ko)[→ 확장 프로그램 관리](https://support.google.com/chrome_webstore/answer/2664769?hl=ko)
* [Microsoft Edge에서 확장 추가, 해제 또는 제거](https://support.microsoft.com/ko-kr/microsoft-edge/microsoft-edg-9c0ec68c-2fbc-2f2c-9ff0-bdc76f46b026)



## 다른 네트워크에서 확인하기

시크릿 모드에서도 계속 문제가 발생한다면 다른 네트워크(예: 휴대폰 핫스팟 등)를 연결했을 때도 같은 문제가 반복되는지 확인해 보세요. 다른 네트워크에서는 문제가 발생하지 않는다면 이는 사용 중인 네트워크의 보안 문제일 수 있습니다.

### 다른 네트워크에서는 정상 동작한다면

다른 네트워크에서 문제가 발생하지 않는다면, 사용 중인 네트워크의 보안 설정이 원인일 가능성이 큽니다. 내부 담당자분께 \*.stibee.com 을 예외 처리해 달라고 요청해 주시면 됩니다.





위 내용을 확인했으나 문제가 계속된다면 아래 도움말을 참고해 문제를 해결해 보세요.

{% content-ref url="email-content-mismatch.md" %}
[email-content-mismatch.md](email-content-mismatch.md)
{% endcontent-ref %}

{% content-ref url="subscriber-upload-issues.md" %}
[subscriber-upload-issues.md](subscriber-upload-issues.md)
{% endcontent-ref %}

{% content-ref url="email-not-received.md" %}
[email-not-received.md](email-not-received.md)
{% endcontent-ref %}

{% content-ref url="editor-text-bold-appearance.md" %}
[editor-text-bold-appearance.md](editor-text-bold-appearance.md)
{% endcontent-ref %}
