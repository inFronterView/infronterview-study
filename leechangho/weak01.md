# 목차
- [JavaScript](#javascript)
  - [1. EcmaScript와 JavaScript의 차이점은 무엇인가요?](#1-ecmascript와-javascript의-차이점은-무엇인가요)
  - [2. 자바스크립트의 자료형(타입)에는 어떤 것들이 있나요?](#2-자바스크립트의-자료형타입에는-어떤-것들이-있나요)
  - [3. Document Object Model이란 무엇인가요?](#3-document-object-model이란-무엇인가요)
  - [4. 이벤트 위임이란 무엇인가요? 이벤트 캡쳐링과 이벤트 버블링의 차이점은 무엇인가요?](#4-이벤트-위임이란-무엇인가요-이벤트-캡쳐링과-이벤트-버블링의-차이점은-무엇인가요)
  - [5. `event.target`과 `event.currentTarget`의 차이점에 대해 설명해보세요.](#5-eventtarget과-eventcurrenttarget의-차이점에-대해-설명해보세요)
  - [6. Call by value와 Call by reference의 차이점은 무엇인가요?](#6-call-by-value와-call-by-reference의-차이점은-무엇인가요)

- [React](#react)
  - [1. 브라우저에 URL을 입력한 순간부터 화면에 웹 페이지가 나타나기까지의 모든 과정을 아는대로 최대한 자세히 설명해보세요.](#1-브라우저에-url을-입력한-순간부터-화면에-웹-페이지가-나타나기까지의-모든-과정을-아는대로-최대한-자세히-설명해보세요)
  - [2. `package.json`, `package-lock.json`, `node_modules`는 무엇인가요?](#2-packagejson-package-lockjson-node_modules는-무엇인가요)
  - [3. Client Side Rendering이란 무엇인가요?](#3-client-side-rendering이란-무엇인가요)
  - [4. Single Page Application이란 무엇인가요?](#4-single-page-application이란-무엇인가요)
  - [5. 상태 변화에 대해 React는 어떻게 반응할까요?](#5-상태-변화에-대해-react는-어떻게-반응할까요)
  - [6. 리액트의 Strict Mode는 어떤 역할을 하는 것인지 최대한 자세히 설명해보세요.](#6-리액트의-strict-mode는-어떤-역할을-하는-것인지-최대한-자세히-설명해보세요)

<br>

# JavaScript
## 1. EcmaScript와 JavaScript의 차이점은 무엇인가요?

### 답변:

### 개념 정리
  #### 1-1. ECMAScript
  - ECMA-262: 범용 목적의 스크립트 언어에 대한 명세, 기술 규격.
  - ECMAScript: JavaScript의 표준 명세를 담은 공식 문서.
  ECMA-262 기술 규격에 의해 정의된 범용 스크립트 언어.
  - 기술 전반에 대한 포괄적인 지침을 제공.
  - 공식 명칭은 ECMA-262.
  - ECMA international에서 제정한 표준.
  - JavaScript를 비롯한 여러 스크립트 언어의 기초가 되는 사양을 정의.<br>
  &nbsp;&nbsp;*비유) ECMA-262: 국어(표준어).<br>
  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;ECMA International: 국립국어원.<br>
  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;ECMAScript: 맞춤법.<br>

  #### 1-2. JavaScript
  - JavaScript: ECMAScript의 표준을 기반으로 하는 스크립트 언어.
  - Netscape에서 처음 개발.<br>
    &nbsp;&nbsp;*비유) JavaScript: 방언.

<br>

## 2. 자바스크립트의 자료형(타입)에는 어떤 것들이 있나요?

### 답변:

### 개념 정리

#### JavaScript의 자료형(타입)
**원시 타입 (Primitive Type)**:

- **string**: 텍스트 데이터를 표현하는 타입
- **number**: 숫자 데이터를 표현하는 타입 (정수와 실수를 포함)
- **boolean**: 참(true) 또는 거짓(false)을 표현하는 타입
- **undefined**: 값이 할당되지 않은 변수의 타입
- **null**: 값이 없음을 명시적으로 표현하는 타입
- **symbol**: 고유하고 변경 불가능한 값 (ES6에서 도입)
- **bigint**: 아주 큰 정수를 표현하는 타입 (ES2020에서 도입)

<br>

**객체 타입 (Object Type)**:
- **Object**: 자바스크립트의 기본 객체 타입으로, 다양한 키-값 쌍을 가질 수 있습니다.
- **Array**: 순서가 있는 데이터 집합을 표현하는 객체 타입
- **Function**: 실행 가능한 코드를 표현하는 객체 타입
- **Date**: 날짜 객체
- **RegExp**: 정규 표현식 객체
- **Map**: 키-값 쌍을 저장하는 객체.
    - 모든 자료형을 키로 사용 가능(객체, 함수, 원시 등)
    - 삽입된 순서대로 요소를 순회 가능(iterate).
- **Set**: 중복되지 않는 값을 저장하는 객체
- **WeakMap**: 약한 참조를 사용하는 키-값 쌍을 저장하는 객체.
    - 키는 반드시 객체.
- **WeakSet**: 약한 참조를 사용하는 중복되지 않는 값을 저장하는 객체

<br>

## 3. Document Object Model이란 무엇인가요?

### 답변:

### 개념 정리

#### DOM(Document Object Model)
- **DOM**: HTML, XML 문서의 구조화된 표현.
  문서를 '트리 구조'로 표현하며, 각 요소는 '트리 노드'로 표현됨.
- JavaScript는 DOM에 접근하여 문서의 내용을 동적으로 수정 가능.
- DOM은 프로그래밍 언어에 독립적이다.

<br>

## 4. 이벤트 위임이란 무엇인가요? 이벤트 캡쳐링과 이벤트 버블링의 차이점은 무엇인가요?

### 답변:

### 개념 정리

#### 이벤트 위임(Event delegation)
- 요소의 '공통 조상'에 이벤트 핸들러를 '단 하나'만 할당해도 여러 요소를 다룰 수 있다.
- 메모리 효율 ↑, 동적 추가 요소도 자동으로 이벤트 처리 가능.
#### 4-1. 이벤트 캡쳐링(Event Capturing)
- 이벤트가 최상위 요소에서 시작하여 이벤트가 발생한 요소까지 도달하는 방식.
- `addEventListener`의 세 번째 인자로 `true`를 전달하여 이벤트 캡쳐링 사용 가능.
- 즉, 상위 → 하위 전파.

#### 4-2. 이벤트 버블링(Event Bubbling)
- 이벤트가 발생한 요소에서 시작하여, 최상위 요소로 전달되는 방식.
- 기본적으로 JavaScript는 이벤트 버블링을 사용한다.
- 즉, 하위 → 상위 전파.

## 5. `event.target`과 `event.currentTarget`의 차이점에 대해 설명해보세요.

### 답변:

### 개념 정리

#### 5. `event.target` VS `event.currentTarget`
- `event.target`: 이벤트가 '실제로 발생한' 요소.
  - 버튼 클릭 시, 내부의 텍스트 요소를 클릭할 경우.
  `event.target` = 텍스트 요소.
- `event.currentTarget`: 이벤트 핸들러가 부착된 요소.
  - 이벤트 위임을 사용한 경우, `event.currentTarget` = 이벤트 핸들러가 부착된 부모 요소.

<br>

## 6. Call by value와 Call by reference의 차이점은 무엇인가요?

### 답변:

### 개념 정리

#### 6. Call by Value, Call by Reference, Call by Sharing.

#### 6-1. Call by Value.
- 함수에 인수를 전달 할 때, '값'을 복사하여 전달.
- 함수 내부에서 인수의 값을 변경해도, **원래의 변수엔 영향 X**.
- `number`,`string`, `boolean`, `null`, `undefined`, `symbol`, `bigint`.

#### 6-2. Call by Reference.
- 함수에 인수를 전달할 때, '참조(메모리 주소)'를 전달.
- 함수 내부에서 인수의 값을 변경하면, **원래 변수에도 영향 O**.
- `object`, `array` etc.

### 6-3. Call by Sharing.
- Javascript는 사실 Call by Reference가 아닌, Call by Sharing 이다?
- 예시<br>
a. 변수 선언
```js
const obj1 = { name: "change me plz"};
const obj2 = { name: "change me plz"};

```

<img width="500" alt="Call by Share-01" src="./Public/weak01/Call by Sharing-01.png">
<br><br>

b. 함수 선언 후, 호출
```js
function change(ref1, ref2) {
  ref1.name = "change!";
  ref2 = { name: "changed!"};

  console.log(ref1, ref2);
}

change(obj1, obj2);
```
<img width="500" alt="Call by Share-02" src="./Public/weak01/Call by Sharing-02.png">

*JS에선 사실 **참조값에 대한 복사본을 만들어 전달**한다.
<br><br>

*`obj1`의 경우
<img width="500" alt="Call by Share-03" src="./Public/weak01/Call by Sharing-03.png">

*`obj2`의 경우
<img width="500" alt="Call by Share-04" src="./Public/weak01/Call by Sharing-04.png">
- 새로운 객체 메모리 주소로 인해 수정 X
<br><br>

*결과
```js
// obj1 = { name: changed!};
// obj2 = { name: change me plz};
```

<br>

# React

## 1. 브라우저에 URL을 입력한 순간부터 화면에 웹 페이지가 나타나기까지의 모든 과정을 아는대로 최대한 자세히 설명해보세요.

### 답변:

### 개념 정리

### URL 입력 후, 웹 페이지 로딩까지의 과정.
a. URL 도메인을 DNS 서버를 통해 조회 → IP 주소로 변환.<br>
*DNS?: Domain Name System.<br>
즉, 도메인이 어떤 IP와 연결돼 있는지 찾아서 변환.<br><br>
b. TCP(Transmission Control Protocol) 연결 시도.
- TCP 3-way handshake를 통해 연결을 설정.<br>
*3-way Handshake?:
	1.	SYN (Synchronize):
	클라이언트(데이터를 보내려는 측)가 서버(데이터를 받으려는 측)에게 연결을 요청하면서 “SYN” 패킷을 보냄. 이 패킷은 클라이언트의 초기 순서 번호(ISN, Initial Sequence Number)를 포함. 이 순서 번호는 이후에 주고받는 데이터 패킷의 순서를 관리하는 데 사용.
	2.	SYN-ACK (Synchronize-Acknowledgment):
	서버는 클라이언트의 요청을 받으면, 클라이언트에게 연결 요청을 수락한다는 응답으로 “SYN-ACK” 패킷을 보냄. 이 패킷은 서버의 초기 순서 번호와 클라이언트가 보낸 순서 번호에 대한 확인 응답(ACK)을 포함하고 있음.
	3.	ACK (Acknowledgment):
	클라이언트는 서버로부터 “SYN-ACK” 패킷을 받으면, “ACK” 패킷을 서버로 보내면서 연결이 확립됐음을 알림. 이 패킷은 서버의 순서 번호에 대한 확인 응답을 포함해. 이제 클라이언트와 서버 간에 데이터 전송이 가능한 상태가 됨.

c. 서버 처리 및 응답(REST API).<br>
d. 클라이언트 응답 수신.
e. 렌더링 과정 수행.
- DOM 트리 생성 후, CSSOM 트리 생성.
- 트리 결합 후, 레이아웃 결정.

f. JavaScript 실행.
- 렌더링 중, `<script>` 발견 시 스크립트를 실행 하여 작업 수행.

g. Painting 수행.
- 실제 화면에 그려지는 픽셀을 결정.
- 최종적으로 화면에 페이지 렌더링.

<br>

## 2. `package.json`, `package-lock.json`, `node_modules`는 무엇인가요?

### 답변:

### 개념 정리
- `package.json`
  - 프로젝트의 메타데이터 포함.
  - npm 패키지 목록, 스크립트, 버전 정보 등.
  - 의존성 관리.
- `package-lock.json`
  - package.json에서 정의한 의존성의 정확한 버전 및 하위 의존성.
  - 다른 개발자가 동일한 환경을 재현할 수 있게 한다.
- `node_modules`
  - 의존성 패키지들이 실제로 설치되는 장소.

<br>

## 3. Client Side Rendering이란 무엇인가요?

### 답변:

### 개념 정리

- CSR(Client Side Rendering)
  - 웹 페이지의 렌더링이 클라이언트에서 이루어지는 방식.
  - 초기 요청 시, 최소한의 HTML만 서버에서 전달 받음.
  - 이후 JavaScript를 통해 동적으로 나머지 콘텐츠를 로드.
    - **장점:** 페이지 전환이 빠르며, 사용자와의 상호작용에 반응이 빠릅니다. 자바스크립트 프레임워크(React, Vue.js 등)와 함께 사용되어, SPA(Single Page Application)를 구현할 때 주로 사용됩니다.
    - **단점:** 초기 로딩 시간이 길어질 수 있으며, 검색 엔진 최적화(SEO)가 어려울 수 있습니다. 또한, JavaScript가 비활성화된 환경에서는 페이지가 제대로 작동하지 않을 수 있습니다.

<br>

## 4. Single Page Application이란 무엇인가요?

### 답변:

### 개념 정리

- SPA(Single Page Application)
  - 사용자가 다른 페이지 이동 시, 전체 페이지를 다시 로드하지 않고, 현재 페이지의 콘텐츠만 동적으로 바꾸는 Web Application.
  - **동작 원리:** 사용자가 페이지를 요청하면 서버는 하나의 HTML 파일을 보내고, 이후의 모든 페이지 전환은 자바스크립트를 통해 클라이언트 측에서 처리됩니다. 서버와의 데이터 통신은 주로 AJAX를 통해 이루어지며, 필요한 데이터만 교환합니다.
  - **장점:** 사용자 경험이 향상되며, 페이지 전환 속도가 매우 빠릅니다. 서버의 부담을 줄이고, 클라이언트 측에서 로직을 처리할 수 있습니다.
  - **단점:** 초기 로딩이 느릴 수 있으며, 복잡한 상태 관리가 필요할 수 있습니다. 또한, SEO 최적화에 대한 추가 작업이 필요합니다.

<br>

## 5. 상태 변화에 대해 React는 어떻게 반응할까요?

### 답변:

### 개념 정리

- 상태 변경 시, 가상 DOM을 사용하여 변경된 부분만 효율적으로 업데이트.
  1. 상태 변경: React가 변화를 감지.
  2. 가상 DOM 업데이트: 새로운 상태를 바탕으로 가상 DOM을 업데이트. 이전 가상 DOM과 비교하여, 반영 할 변경 사항을 계산.
  3. DOM 업데이트: 필요한 부분만 실제 DOM에 반영하여 UI를 업데이트.

<br>

## 6. 리액트의 Strict Mode는 어떤 역할을 하는 것인지 최대한 자세히 설명해보세요.

## 답변:

## 개념 정리

- Strict Mode는 리액트에서 잠재적인 문제를 감지하고 경고하는 데 도움을 주는 개발 도구.
  - **안전하지 않은 생명주기 메서드 감지**: 리액트에서 권장되지 않는 생명주기 메서드 사용 시 경고를 발생시킵니다.

  - **의심스러운 코드 감지**: 예를 들어, 배치(batch)되지 않은 상태 업데이트나 불안정한 레퍼런스 같은 코드를 감지하고 경고를 발생시킵니다.

  - **기타 부작용 감지**: 추가적인 리렌더링을 유발하거나, 비동기적 작업에서 발생할 수 있는 문제를 감지합니다.