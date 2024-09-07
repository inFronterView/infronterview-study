# 목차

- JavaScript
  - [EcmaScript와 JavaScript의 차이점은 무엇인가요?](#ecmascript와-javascript의-차이점은-무엇인가요)
  - [자바스크립트의 자료형(타입)에는 어떤 것들이 있나요?](#자바스크립트의-자료형타입에는-어떤-것들이-있나요)
  - [Document Object Model이란 무엇인가요?](#document-object-model이란-무엇인가요)
  - [이벤트 위임이란 무엇인가요? 이벤트 캡쳐링과 이벤트 버블링의 차이점은 무엇인가요?](#이벤트-위임이란-무엇인가요-이벤트-캡쳐링과-이벤트-버블링의-차이점은-무엇인가요)
  - [event.target과 event.currentTarget의 차이점에 대해 설명해보세요.](#eventtarget과-eventcurrenttarget의-차이점에-대해-설명해보세요)
  - [Call by value와 Call by reference의 차이점은 무엇인가요?](#call-by-value와-call-by-reference의-차이점은-무엇인가요)
- React
  - [브라우저에 URL을 입력한 순간부터 화면에 웹 페이지가 나타나기까지의 모든 과정을 아는대로 최대한 자세히 설명해보세요.](#브라우저에-url을-입력한-순간부터-화면에-웹-페이지가-나타나기까지의-모든-과정을-아는대로-최대한-자세히-설명해보세요)
  - [package.json, package-lock.json, node_modules는 무엇인가요?](#packagejson-package-lockjson-node_modules는-무엇인가요)
  - [Client Side Rendering이란 무엇인가요?](#client-side-rendering이란-무엇인가요)
  - [Single Page Application이란 무엇인가요?](#single-page-application이란-무엇인가요)
  - [상태 변화에 대해 React는 어떻게 반응할까요?](#상태-변화에-대해-react는-어떻게-반응할까요)
  - [리액트의 Strict Mode는 어떤 역할을 하는 것인지 최대한 자세히 설명해보세요.](#리액트의-strict-mode는-어떤-역할을-하는-것인지-최대한-자세히-설명해보세요)

<br>

# Javascript

## EcmaScript와 JavaScript의 차이점은 무엇인가요?

> JavaScript는 EcmaScript 표준을 따르는 구현체이며 EcmaScript는 JavaScript의 기능을 정의하는 명세서라고 할 수 있습니다.<br>

    ECMAScript는 규격이고, JavaScript는 이 규격을 구현한 언어입니다.<br>
    JavaScript는 ECMAScript 외에도 브라우저 환경에서 사용할 수 있는 추가 기능을 포함합니다.<br>
    ECMAScript 버전이 업데이트되면 JavaScript도 새로운 기능을 구현합니다.

### ECMAScript

- Ecma International에서 ECMA-262 기술 규격에 따라 정의한 표준화된 스크립트 프로그래밍 언어입니다.
- 이는 언어의 핵심 기능과 문법을 정의합니다.
- ES6, ES7 등 버전이 존재하며, 새로운 기능이 추가될 때마다 업그레이드됩니다.

### JavaScript

- ECMAScript 사양을 기반으로 만들어진 실제 프로그래밍 언어입니다.
- JavaScript는 ECMAScript의 기능을 포함하면서도 추가적인 기능(예: DOM 조작, 웹 API 등)을 제공합니다.
- 브라우저와 호환되는 엔진(V8, SpiderMonkey 등)에 의해 동작합니다.

<br>

## 자바스크립트의 자료형(타입)에는 어떤 것들이 있나요?

> 기본(원시) 타입

- Number: 숫자 (예: 42, 3.14)
- String: 문자열 (예: "Hello", 'World')
- Boolean: 논리값 (true 또는 false)
- Undefined: 값이 할당되지 않은 상태
- Null: 의도적으로 값이 없음을 나타내는 상태
- Symbol: ES6에서 추가된 고유한 식별자 (예: Symbol('id'))
- BigInt: ES11에서 추가된 큰 정수를 다루기 위한 타입 (예: 1234567890123456789n)

> 객체 타입

- Object: 키-값 쌍의 집합 (예: {name: "John", age: 30})
- Array: 순서가 있는 값의 집합 (예: [1, 2, 3])
- Function: 실행 가능한 코드 블록
- Date: 날짜와 시간을 나타내는 객체
- RegExp: 정규 표현식 객체(Regular Expression)
- Map, Set

<br>

## Document Object Model이란 무엇인가요?

> Document Object Model (DOM)은 웹 페이지의 구조화된 표현으로,HTML 또는 XML 문서를 트리 구조로 나타낸 것입니다.

주요 특징

- **트리 구조**: DOM은 문서를 트리 구조로 나타내며, 각 노드는 부모-자식 관계를 가집니다.
- **동적 수정**: DOM을 통해 웹 페이지의 요소를 동적으로 생성, 삭제, 수정할 수 있습니다.
- **이벤트 처리**: DOM을 사용해 웹 페이지에서 발생하는 다양한 이벤트(클릭, 키보드 입력 등)를 처리할 수 있습니다.

<br>

## 이벤트 위임이란 무엇인가요? 이벤트 캡쳐링과 이벤트 버블링의 차이점은 무엇인가요?

> 이벤트 위임은 여러 요소에 대해 이벤트 핸들러를 개별적으로 추가하는 대신,<br>
> 상위 요소에 하나의 이벤트 핸들러를 추가하여 하위 요소들의 이벤트를 관리하는 기법입니다.<br>
> 이벤트가 버블링 또는 캡쳐링 단계에서 상위 요소까지 도달하기 때문에 상위 요소에서 이벤트를 잡아 처리할 수 있습니다.

> 이벤트 캡처링은 최상위 요소에서 시작하여, 이벤트가 발생한 요소까지 내려갑니다.<br>

    이벤트 버블링은 이벤트가 발생한 요소에서 시작하여 최상위 요소로 올라갑니다.<br>
    이벤트 캡처링이 먼저 발생하고 그다음 이벤트 버블링이 발생합니다.<br>
    대부분의 부라우저에서 이벤트 버블링이 기본 동작입니다.<br>
    이벤트 캡처링을 사용하려면 명시적으로 설정해야 합니다.

<br>

## event.target과 event.currentTarget의 차이점에 대해 설명해보세요.

> **event.target**은 **실제로 이벤트가 발생한 요소**를 가리키고,<br>

    **event.currentTarget**은 **이벤트 핸들러가 붙어있는 요소**를 가리킵니다.<br>
    즉, 이벤트가 위임되었을 때, `target`은 이벤트가 발생한 하위 요소고, `currentTarget`은 이벤트를 듣고 있는 부모 요소입니다.

- **`event.target`**
  - 이벤트가 발생한 실제 요소를 가리킵니다.
  - 사용자가 클릭한 요소나 마우스를 올린 요소와 같이, 이벤트가 발생한 원래의 요소를 의미합니다.
- **`event.currentTarget`**
  - 현재 이벤트가 처리 중인 요소를 가리킵니다.
  - 이벤트 리스너가 부착된 요소입니다.
  - `event.currentTarget`을 사용하여 이벤트 핸들러가 연결된 상위 요소를 참조할 수 있습니다.
  - `event.currentTarget`은 이벤트 핸들러 내부에서 `this`키워드와 동일한 값을 가집니다. (`this` 바인딩을 생성하지 않는 화살표 함수 제외)

```jsx
// 예시
<div id="outer">
  <div id="inner">
    <button id="button">Click me</button>
  </div>
</div>

<script>
document.getElementById("outer").addEventListener("click", function(e) {
    console.log("Target:", e.target.id);
    console.log("CurrentTarget:", e.currentTarget.id);
});
</script>

// 버튼 클릭시
// e.target.id는 "button"
// e.currentTarget.id는 "outer"
```

<br>

## Call by value와 Call by reference의 차이점은 무엇인가요?

> Call by Value는 함수에 값을 복사해서 전달하기 때문에 함수 내에서 값이 변경되어도 원래 변수에는 아무런 영향이 없습니다.<br>
> Call by Reference는 변수의 참조(주소)를 전달하여, 함수 내에서 값이 변경되면 원래 변수에도 그 변경이 반영됩니다.

Call by value (값에 의한 호출)

- 함수에 인자로 값의 복사본이 전달됩니다.
- 원본 값은 변경되지 않습니다.
- JavaScript에서 원시 타입(Number, String, Boolean 등)은 Call by value로 전달됩니다.

```jsx
// 예시
function changeValue(x) {
  x = 10;
}

let a = 5;
changeValue(a);
console.log(a); // 출력: 5 (변경되지 않음)
```

Call by reference (참조에 의한 호출)

- 함수에 인자로 값의 메모리 주소(참조)가 전달됩니다.
- 함수 내에서 인자를 변경하면 원본 값도 변경됩니다.
- JavaScript에서 객체는 Call by reference와 유사하게 동작합니다.

```jsx
// 예시
function changeObject(obj) {
  obj.prop = 10;
}

let obj = { prop: 5 };
changeObject(obj);
console.log(obj.prop); // 출력: 10 (변경됨)
```

<br><br>

# React

## 브라우저에 URL을 입력한 순간부터 화면에 웹 페이지가 나타나기까지의 모든 과정을 아는대로 최대한 자세히 설명해보세요.

1. DNS 조회
   - 브라우저는 입력된 도메인 이름을 IP 주소로 변환합니다.
   - 로컬 DNS 캐시 확인 후, 필요시 ISP의 DNS 서버에 요청을 보냅니다.
2. TCP 연결 수립
   - 얻은 IP 주소로 웹 서버와 TCP 연결을 시도합니다.
     - **3-way handshake** 과정을 통해 연결이 수립됩니다 (SYN, SYN-ACK, ACK).
3. TLS 핸드셰이크 (HTTPS의 경우)
   - 보안 연결이 필요한 경우 TLS 핸드셰이크가 진행됩니다.
     - 서버의 인증서 확인, 암호화 방식 협상 등이 포함됩니다.
4. HTTP 요청 전송
   - 브라우저가 서버에 HTTP GET 요청을 보냅니다.
     - 요청 헤더에는 브라우저 정보, 수용 가능한 콘텐츠 유형 등이 포함됩니다.
5. 서버 처리 및 HTTP 응답
   - 서버는 요청을 처리하고 HTML 문서를 포함한 HTTP 응답을 보냅니다.
     - 정적 콘텐츠의 경우 파일을 직접 전송하고, 동적 콘텐츠의 경우 **서버 사이드 스크립트**(예: PHP, Python, Java 등)를 실행하여 콘텐츠를 생성합니다.
     - 응답에는 상태 코드(예: 200 OK), 헤더, 그리고 HTML 문서가 포함됩니다.
6. HTML 파싱 및 DOM 트리 생성
   - 브라우저는 HTML을 파싱하여 DOM 트리를 구성합니다.
7. CSS 처리 및 CSSOM 생성
   - CSS 파일을 다운로드하고 파싱하여 CSSOM을 생성합니다
8. 자바스크립트 실행
   - HTML 파서가 `<script>` 태그를 만나면 자바스크립트 코드를 실행합니다.
   - 자바스크립트는 DOM을 조작하거나 AJAX 요청을 보낼 수 있습니다.
9. 렌더 트리 구축
   - DOM과 CSSOM을 결합하여 **렌더 트리**를 만듭니다.
10. 레이아웃
    - 렌더 트리의 각 노드에 대해 화면상의 정확한 위치와 크기를 계산합니다.
11. 페인팅
    - 레이아웃 정보를 바탕으로 실제 픽셀을 화면에 그립니다.

<br>

## package.json, package-lock.json, node_modules는 무엇인가요?

1. `package.json`은
   - Node.js 프로젝트의 메타데이터를 담고 있는 JSON 파일입니다.
   - 프로젝트 이름, 버전, 설명, 의존성 패키지 목록 등을 포함합니다.
   - `npm init` 명령어로 생성할 수 있습니다.
2. `package-lock.json`은
   - 프로젝트의 의존성 트리를 정확히 기록한 파일입니다.
   - 각 패키지의 정확한 버전과 하위 의존성을 명시합니다.
   - 다른 개발 환경에서도 동일한 의존성 구조를 재현할 수 있게 합니다.
3. `node_modules`은
   - 프로젝트의 의존성 패키지들이 실제로 설치되는 디렉토리입니다.
   - `npm install` 명령어를 실행하면 이 폴더에 패키지들이 다운로드됩니다.
   - 보통 버전 관리 시스템(.gitignore 등)에서 제외됩니다.

<br>

## Client Side Rendering이란 무엇인가요?

> Client Side Rendering (CSR)은 웹 페이지의 콘텐츠가 서버가 아니라 클라이언트(브라우저)에서 렌더링되는 방식입니다.

- 웹 애플리케이션의 렌더링을 클라이언트(브라우저) 측에서 수행하는 방식입니다.
- 서버는 최소한의 HTML과 JavaScript 파일만 제공합니다.
- 클라이언트는 JavaScript를 실행하여 필요한 데이터를 서버로부터 추가 요청하고,
  이를 바탕으로 페이지를 동적으로 구성합니다.
- JavaScript가 브라우저에서 실행되면서 동적으로 콘텐츠를 생성하고 DOM을 조작합니다.
- 초기 로딩 시간이 길 수 있지만, 이후 페이지 전환이 빠릅니다.
- 서버 부하를 줄일 수 있고, 사용자 경험이 향상될 수 있습니다.
- SEO(검색 엔진 최적화)에 불리할 수 있습니다.
- CSR은 SPA(Single Page Application)와 함께 자주 사용되며,
  페이지 간 빠른 전환과 비동기 데이터 로딩을 가능하게 합니다.
  그러나 초기 로드 시간이 길어질 수 있다는 단점이 있습니다.

<br>

## Single Page Application이란 무엇인가요?

> 웹 애플리케이션이 단일 HTML 페이지로 구성되어 있고, 페이지 전환이 전체 페이지를 새로고침하는 것이 아니라 동적으로 이루어지는 애플리케이션입니다.

- 하나의 HTML 페이지로 구성된 웹 애플리케이션입니다.
- 초기 로드 시 모든 HTML, CSS, JavaScript를 로드하고,
  이후 사용자가 인터랙션할 때 필요한 데이터만 서버에서 비동기적으로 받아와서 DOM을 갱신합니다.
- 브라우저 내에서 동적으로 콘텐츠를 업데이트하기 때문에 사용자 경험이 더 매끄럽고 응답성이 좋습니다.
- 라우팅, 상태 관리 등을 클라이언트 측에서 처리합니다.
- SPA의 대표적인 프레임워크로는 React, Angular, Vue.js 등이 있습니다.

<br>

## 상태 변화에 대해 React는 어떻게 반응할까요?

> **React**는 상태가 변경되었을 때 UI를 다시 렌더링하여 사용자가 항상 최신의 UI를 볼 수 있도록 합니다.<br>
> React 컴포넌트 내에서 상태(State)는 `useState`와 같은 훅을 사용하여 관리됩니다.<br>
> 상태가 변경되면 React는 자동으로 해당 컴포넌트를 다시 렌더링합니다.<br>
> React는 효율적인 렌더링을 위해 **Virtual DOM**을 사용합니다.<br>
> 상태 변화에 따라 변경된 부분만 Virtual DOM에서 업데이트한 후, 실제 DOM과 비교하여 차이점만을 반영합니다.<br>
> 이를 통해 최소한의 DOM 조작으로 빠르고 효율적인 업데이트가 가능합니다.

React에서 상태 변화와 리렌더링 과정

1. 이벤트 발생: 사용자 상호작용으로 이벤트가 트리거됩니다.
2. 상태 업데이트 예약: useState의 setter 함수가 호출되어 상태 변경이 예약됩니다.
3. 일괄 처리(Batching): React는 여러 상태 업데이트를 모아서 한 번에 처리합니다. 이는 성능 최적화를 위한 것입니다.
4. 리렌더링 결정: 최종 상태가 이전과 다르면 리렌더링이 시작됩니다.
5. 컴포넌트 함수 실행: 새로운 상태로 컴포넌트 함수가 다시 실행됩니다.
6. 가상 DOM 생성: 새로운 JSX 구조로 가상 DOM이 생성됩니다.
7. 비교(Reconciliation): 이전 가상 DOM과 새 가상 DOM을 비교합니다.
8. 실제 DOM 업데이트: 변경된 부분만 실제 DOM에 적용됩니다.

<br>

## 리액트의 Strict Mode는 어떤 역할을 하는 것인지 최대한 자세히 설명해보세요.

> React의 Strict Mode는 개발 모드에서 사용되는 도구로, 잠재적인 문제를 감지하고 개발 과정에서 더 나은 품질의 코드를 작성하도록 돕기 위해 제공되는 기능입니다.

주요 기능은

- 비권장되는 생명 주기 메서드의 사용을 감지하여 경고를 표시합니다.
- 예를 들어, 예상치 못한 부작용이 발생할 수 있는 부분을 감지하여 개발자가 문제를 사전에 해결할 수 있도록 합니다.
- 비동기 작업이 의도한 대로 동작하지 않을 때 경고를 제공합니다.
- 일부 생명주기 메서드를 이중으로 호출하여 부작용을 찾아냅니다.
- 동일한 키를 가진 중복된 요소가 있을 경우 경고를 표시합니다.
- 문자열 ref 대신 함수형 ref나 createRef를 사용하도록 권장합니다.
- useEffect 클린업 함수의 누락을 감지합니다.
