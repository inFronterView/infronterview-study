# 목차

- JavaScript
  - [EcmaScript와 JavaScript의 차이점은 무엇인가요?](#ecmascript와-javascript의-차이점은-무엇인가요)
  - [자바스크립트의 자료형(타입)에는 어떤 것들이 있나요?](#자바스크립트의-자료형타입에는-어떤-것들이-있나요)
  - [Document Object Model이란 무엇인가요?](#document-object-model이란-무엇인가요)
  - [이벤트 위임이란 무엇인가요? 이벤트 캡쳐링과 이벤트 버블링의 차이점은 무엇인가요?](#이벤트-위임이란-무엇인가요-이벤트-캡쳐링과-이벤트-버블링의-차이점은-무엇인가요)
  - [event.target과 event.currentTarget의 차이점에 대해 설명해보세요.](#eventtarget과eventcurrenttarget의-차이점에-대해-설명해보세요)
  - [Call by value와 Call by reference의 차이점은 무엇인가요?](#call-by-value와-call-by-reference의-차이점은-무엇인가요)
- React
  - [브라우저에 URL을 입력한 순간부터 화면에 웹 페이지가 나타나기까지의 모든 과정을 아는대로 최대한 자세히 설명해보세요.](#브라우저에-url을-입력한-순간부터-화면에-웹-페이지가-나타나기까지의-모든-과정을-아는대로-최대한-자세히-설명해보세요)
  - [package.json, package-lock.json, node_modules는 무엇인가요?](#packagejsonpackage-lockjsonnode_modules는-무엇인가요)
  - [Client Side Rendering이란 무엇인가요?](#client-side-rendering이란-무엇인가요)
  - [Single Page Application이란 무엇인가요?](#single-page-application이란-무엇인가요)
  - [상태 변화에 대해 React는 어떻게 반응할까요?](#상태-변화에-대해-react는-어떻게-반응할까요)
  - [리액트의 Strict Mode는 어떤 역할을 하는 것인지 최대한 자세히 설명해보세요.](#리액트의-strict-mode는-어떤-역할을-하는-것인지-최대한-자세히-설명해보세요)

<br>

# JavaScript

## EcmaScript와 JavaScript의 차이점은 무엇인가요?

EcmaScript는 JavaScript의 표준화된 사양이며, JavaScript는 이 사양을 구현한 프로그래밍 언어입니다. <br> EcmaScript는 언어의 핵심 기능과 문법을 정의하는 반면, JavaScript는 이러한 사양을 바탕으로 실제 실행 환경에서 동작하는 언어입니다. <br>
EcmaScript는 Ecma International이라는 표준화 기구에 의해 관리되며, 정기적으로 새로운 버전이 발표됩니다. 각 버전은 언어에 새로운 기능과 개선사항을 도입합니다. JavaScript는 이러한 EcmaScript 사양을 준수하면서도, 브라우저나 Node.js와 같은 실행 환경에 특화된 추가적인 API와 기능을 포함합니다.

### 🧐 관련해서 알아두면 좋을 것들

<details>
<summary>
  <b>EcmaScript 주요 업데이트</b>
</summary>
<br/>

**EcmaScript2015 (ES6)**

- let, const
- 화살표 함수
- 클래스 문법
- 템플릿 리터럴
- 구조 분해 할당
- Promise

**EcmaScript2017 (ES8)**

- async/await

**EcmaScript2020 (ES11)**

- 옵셔널 체이닝 (?.)
- Nullish 병합 연산자 (??)

</details>

<details>
<summary>
  <b>Web API</b>
</summary>
<br/>

Web API는 웹 브라우저에서 제공하는 프로그래밍 인터페이스입니다. JavaScript 를 사용하여 웹 페이지나 웹 앱에서 다양한 기능을 구현할 수 있게 해줍니다. <br>
WHATWG와 W3C가 Web API의 표준화를 주도하며, JavaScript 언어로 Web API 를 사용하지만, Web API 자체는 JavaScript의 일부가 아닙니다. <br>

Web API 예시: DOM API, Fetch API, WebGL 등..

</details>

<br>

## 자바스크립트의 자료형(타입)에는 어떤 것들이 있나요?

**Primitive Type (기본 타입, 원시 값) 불변 값 (객체형 이외 모든 값)**

- Number
- String
- Boolean
- Null
- Undefined
- Symbol (ES6 추가)
- BigInt (ES11 추가)

**Object Type (객체 타입, 참조 값) 유일한 변경 가능한 값**

- Object: 키-값 쌍의 집합체
- Array: 순서가 있는 요소의 집합
- Function: 실행 가능한 코드 블록
- Date: 날짜와 시간을 나타내는 객체
- RegExp: 정규 표현식 객체 (Regular Expression)
- Map, Set

### 🧐 관련해서 알아두면 좋을 것들

<details>
<summary>
  <b>불변 값</b>
</summary>
<br/>

- 원시 값은 불변하여 변형할 수 없다. 원시 값 자체와, 원시 값을 할당한 변수를 혼동하지 않아야합니다. 변수는 새로운 값을 다시 할당할 수 있지만, 이미 생성한 원시 값은 객체, 배열, 함수와 달리 변형할 수 없습니다.
- `typeof null`은 `object`이다 `null`을 확인하려면 `=== null` (일치연산자)로 확인해야 합니다.

</details>

<details>
<summary>
  <b>JavaScript는 동적 타입 언어</b>
</summary>
<br/>

JavaScript 가 동적 타입 언어라는 것은 변수의 타입이 미리 선언되지 않고 런타임에 결정된다는 의미입니다. <br>
변수 x의 타입은 어떤 값이 할당되느냐에 따라 실행 중에 계속 변할 수 있습니다. 이는 컴파일 시점에 타입이 결정되는 정적 타입 언어 (Java, C++)와는 다른 특징입니다. <br>
동적 타이핑은 유연성을 제공하지만, 동시에 타입 관련 오류를 런타임에서야 발견할 수 있다는 단점도 있습니다.
이를 보완하기 위해 TypeScript와 같은 정적 타입 검사 도구를 사용하기도 합니다.

</details>

<br>

## Document Object Model이란 무엇인가요?

DOM(문서 객체 모델)은 HTML, XML 문서의 각 항목을 계층으로 표현하여 생성, 변경, 삭제할 수 있도록 돕는 인터페이스 입니다. <br>
웹 페이지의 구조화된 표현을 제공하며, 주로 JavaScript가 문서 구조, 스타일, 내용을 변경할 수 있게 합니다. <br>
DOM은 문서를 노드와 객체의 트리로 표현합니다. HTML 요소, 속성, 텍스트 등이 노드가 됩니다. <br>
JavaScript를 통해 DOM을 조작할 수 있어, 동적인 웹 페이지 생성이 가능합니다. <br>
DOM은 웹 개발에서 핵심적인 개념으로, 동적이고 상호작용적인 웹 페이지를 만드는 데 필수적입니다.

<br>

## 이벤트 위임이란 무엇인가요? 이벤트 캡쳐링과 이벤트 버블링의 차이점은 무엇인가요?

이벤트 위임은 여러 요소에 대해 각각 이벤트 핸들러를 연결하는 대신, 그 요소들의 공통 조상에 하나의 이벤트 핸들러를 연결하는 기법입니다. 이렇게 하면, 동적으로 추가된 요소들에 대해서도 이벤트 처리가 가능해 집니다. 이는 이벤트 버블링을 활용한 패턴이라고 볼 수 있습니다. <br>
이벤트 전파는 DOM 트리를 통해 이벤트가 이동하는 방식을 설명하며, 이벤트 캡쳐링 단계, 이벤트 타겟 단계, 이벤트 버블링 세 가지 단계가 있습니다. <br>
이벤트 캡처링은 이벤트가 최상위 요소에서 시작하여 타겟 요소까지 내려가는 단계이며, 이벤트 타겟 단계는 이벤트가 이벤트 타겟에 도달한 단계를 의미합니다. 이벤트 버블링은 이벤트가 타겟 요소에서 시작하여 최상위 요소까지 올라가는 단계입니다.

<br>

## `event.target`과 `event.currentTarget`의 차이점에 대해 설명해보세요.

`event.target`은 이벤트가 실제로 발생한 요소를 가리킵니다. 이는 이벤트 버블링 과정에서 변하지 않으며, 사용자가 직접 상호작용한 DOM 요소를 참조합니다. <br>
`event.currentTarget`은 현재 이벤트 핸들러가 동작하고 있는 요소를 가리킵니다. 이는 항상 이벤트 리스너가 부착된 요소를 참조하며, 이벤트 버블링 과정에서 변할 수 있습니다. <br>
이벤트 위임 패턴에서 이 차이는 중요합니다. `event.target`을 사용하여 실제 클릭된 하위 요소를 식별하고, `event.currentTarget`을 사용하여 이벤트 핸들러가 연결된 상위 요소를 참조할 수 있습니다.<br>
`event.currentTarget`은 이벤트 핸들러 내부에서 `this`키워드와 동일한 값을 가집니다. (`this` 바인딩을 생성하지 않는 화살표 함수 제외)

<br>

## Call by value와 Call by reference의 차이점은 무엇인가요?

Call by value(값에 의한 호출)는 함수 호출 시 인자로 전달되는 **값의 복사본**이 함수의 매개변수로 전달됩니다. 이 경우 함수 내에서 매개변수를 변경해도 원본 값에는 영향을 미치지 않습니다. <br>
주로 기본 데이터 타입(숫자, 문자열, 불리언 등)에 적용됩니다. <br>
Call by reference(참조에 의한 호출)는 함수 호출 시 인자로 전달되는 **값의 메모리 주소**가 함수의 매개변수로 전달됩니다. 이 경우 함수 내에서 매개변수를 변경하면 원본 값도 함께 변경됩니다. <br>
객체와 배열과 같은 참조 타입에 적용됩니다. <br>
JavaScript에서는 엄밀히 말해 모든 것이 Call by value로 동작하지만, 객체의 경우 그 값이 참조이기 때문에 Call by reference와 유사하게 동작합니다. 이를 'Call by sharing'이라고도 부릅니다. <br>
함수 내에서 매개변수에 새로운 객체를 할당하면 원본 객체에는 영향을 미치지 않지만, **객체의 속성을 변경하면 원본 객체도 함께 변경**됩니다.

### 🧐 관련해서 알아두면 좋을 것들

<details>
<summary>
  <b>원본 객체가 변경되는 부작용을 해결하기 위한 방법들</b>
</summary>
<br/>

- 객체 복사:
  - 얕은 복사: Object.assign({}, obj) 또는 스프레드 연산자 {...obj}를 사용합니다.
  - 깊은 복사: JSON.parse(JSON.stringify(obj))를 사용하거나, lodash의 \_.cloneDeep() 같은 라이브러리를 활용합니다.
- 불변성 유지:
  - 객체를 직접 수정하지 않고, 새로운 객체를 생성하여 반환합니다.
  - React나 Redux 같은 라이브러리에서 많이 사용되는 패턴입니다.
- Object.freeze() 메서드:
  - 객체를 불변으로 만들어 수정을 방지합니다. 단, 얕은 동결만 가능합니다.
- 매개변수 재할당:
  - 함수 내에서 매개변수에 새 객체를 할당하면 원본 객체는 변경되지 않습니다.
- 함수형 프로그래밍 기법:
  - 순수 함수를 사용하여 부작용을 최소화합니다.

**순수함수: 동일한 인자에 대해항상 똑같은 값을 리턴하는 함수**

</details>

<br><br>

# React

## 브라우저에 URL을 입력한 순간부터 화면에 웹 페이지가 나타나기까지의 모든 과정을 아는대로 최대한 자세히 설명해보세요.

브라우저는 먼저 URL을 분석합니다. <br>
브라우저는 로컬 캐시와 호스트 파일을 확인하여 해당 도메인의 IP 주소를 찾습니다. 찾지 못하면 DNS 서버에 쿼리를 보내 IP 주소를 요청합니다. <br>
IP 주소를 얻은 후, 브라우저는 해당 서버와 TCP 연결을 시작합니다. 이는 3-way handshake 과정을 통해 이루어집니다. <br>
연결이 설정되면, 브라우저는 HTTP GET 요청을 서버로 전송합니다. 이 요청에는 원하는 웹 페이지의 경로와 파일명이 포함됩니다. <br>
웹 서버는 요청을 받아 처리하고, HTML 문서와 함께 HTTP 응답을 브라우저로 보냅니다. <br>
브라우저는 받은 HTML을 파싱하여 DOM 트리를 구축합니다. 이 과정에서 추가적인 리소스(CSS, 이미지, 스크립트 등)가 필요하면 서버에 추가 요청을 보냅니다. <br>
CSS 파일을 받으면 CSSOM을 생성하고, DOM과 CSSOM을 결합하여 렌더 트리를 만듭니다. <br>
자바스크립트 파일을 받으면 파싱하고 실행합니다. 이 과정에서 DOM이나 CSSOM이 수정될 수 있습니다. <br>
브라우저는 렌더 트리를 기반으로 레이아웃을 계산하고, 각 요소의 정확한 위치와 크기를 결정합니다. <br>
마지막으로, 페인팅 과정을 통해 실제 픽셀로 화면에 그립니다. <br>
이 모든 과정이 완료되면 사용자는 요청한 웹 페이지를 볼 수 있게 됩니다.

<br>

## `package.json`, `package-lock.json`, `node_modules`는 무엇인가요?

package.json은 Node.js 프로젝트의 메타데이터를 담고 있는 JSON 파일입니다. <br>
이 파일은 프로젝트의 이름, 버전, 설명, 의존성 패키지 목록 등의 정보를 포함합니다. <br>
npm이나 yarn 같은 패키지 매니저는 package.json을 참조하여 필요한 패키지를 설치하고 관리합니다. <br>
package-lock.json은 패키지의 정확한 버전 정보와 의존성 트리를 저장하는 파일입니다. <br>
이 파일은 프로젝트의 의존성 패키지들이 정확히 어떤 버전으로 설치되었는지를 기록하여, 다른 환경에서도 동일한 버전의 패키지를 설치할 수 있게 합니다. <br>
node_modules는 프로젝트의 의존성 패키지들이 실제로 설치되는 디렉토리입니다. <br>
npm이나 yarn이 package.json에 명시된 패키지들을 설치할 때, 이 디렉토리에 해당 패키지들의 코드와 그 패키지들의 의존성 패키지들이 함께 저장됩니다. <br>
이 세 요소는 Node.js 프로젝트의 의존성 관리에 중요한 역할을 하며, 개발자들이 일관된 개발 환경을 유지하고 프로젝트를 쉽게 공유할 수 있게 해줍니다.

<br>

## Client Side Rendering이란 무엇인가요?

Client Side Rendering(CSR)은 웹 애플리케이션의 렌더링 방식 중 하나입니다. <br>
이 방식에서는 서버가 최소한의 HTML 파일과 JavaScript 번들을 클라이언트(브라우저)로 전송합니다. <br>
브라우저는 받은 JavaScript를 실행하여 동적으로 페이지 콘텐츠를 생성하고 렌더링합니다. <br>
CSR은 초기 로딩 후 페이지 전환이 빠르고 서버 부하를 줄일 수 있다는 장점이 있습니다. <br>
하지만 초기 로딩 시간이 길어질 수 있고, 검색 엔진 최적화(SEO)에 불리할 수 있다는 단점도 있습니다. <br>
React, Vue, Angular 같은 현대적인 JavaScript 프레임워크들은 주로 CSR 방식을 사용합니다. <br>
CSR은 동적이고 상호작용이 많은 단일 페이지 애플리케이션(SPA)에 특히 적합한 렌더링 방식입니다.

<br>

## Single Page Application이란 무엇인가요?

Single Page Application(SPA)은 하나의 HTML 페이지로 구성된 웹 애플리케이션입니다. <br>
SPA는 초기에 필요한 모든 리소스(HTML, CSS, JavaScript)를 로드한 후, 사용자 상호작용에 따라 동적으로 콘텐츠를 업데이트합니다. <br>
페이지 전환 시 새로운 페이지를 불러오지 않고, JavaScript를 사용하여 현재 페이지의 내용을 변경합니다.
이 방식은 네이티브 앱과 유사한 부드러운 사용자 경험을 제공할 수 있습니다. <br>
SPA는 대개 RESTful API나 GraphQL과 같은 백엔드 서비스와 통신하여 데이터를 주고받습니다. <br>
React, Vue, Angular 등의 프레임워크를 사용하여 SPA를 개발하는 것이 일반적입니다. <br>
SPA는 빠른 상호작용과 좋은 사용자 경험을 제공하지만, 초기 로딩 시간이 길어질 수 있고 SEO에 불리할 수 있다는 단점이 있습니다.

<br>

## 상태 변화에 대해 React는 어떻게 반응할까요?

React는 컴포넌트의 상태(state) 변화를 감지하고 이에 반응하여 UI를 업데이트합니다. <br>
상태가 변경되면 React는 가상 DOM(Virtual DOM)을 활용하여 변경사항을 효율적으로 처리합니다. <br>
컴포넌트의 setState 메서드나 Hooks의 상태 업데이트 함수가 호출되면 React는 리렌더링 과정을 시작합니다. <br>
React는 변경된 상태를 바탕으로 새로운 가상 DOM 트리를 생성합니다. <br>
이전 가상 DOM과 새로운 가상 DOM을 비교하는 과정을 거치는데, 이를 재조정(Reconciliation)이라고 합니다. <br>
재조정 과정에서 React는 실제로 변경이 필요한 부분만을 식별합니다. <br>
변경이 필요한 부분만 실제 DOM에 적용하여 효율적으로 UI를 업데이트합니다. <br>
이러한 과정을 통해 React는 상태 변화에 따른 UI 업데이트를 최적화하고, 불필요한 DOM 조작을 최소화하여 성능을 향상시킵니다.

<br>

## 리액트의 Strict Mode는 어떤 역할을 하는 것인지 최대한 자세히 설명해보세요.

Strict Mode는 React 애플리케이션의 잠재적인 문제를 식별하는 데 도움을 주는 개발 모드 전용 기능입니다. <br>
이 모드는 애플리케이션을 감싸는 <React.StrictMode> 컴포넌트를 통해 활성화할 수 있습니다. <br>
Strict Mode는 안전하지 않은 생명주기 메서드 사용, 레거시 문자열 ref API 사용, 예상치 못한 부작용 등을 감지하고 경고합니다. <br>
일부 생명주기 메서드를 의도적으로 이중으로 호출하여 부작용을 찾아냅니다. <br>
컴포넌트의 불필요한 부작용을 감지하기 위해 useEffect 내부의 코드를 두 번 실행합니다. <br>
예기치 않은 부작용을 찾기 위해 함수 컴포넌트 전체를 두 번 렌더링합니다. <br>
더 이상 사용되지 않는 API의 사용을 감지하고 경고를 표시합니다. <br>
Strict Mode는 개발 모드에서만 작동하며, 프로덕션 빌드에는 영향을 미치지 않습니다. <br>
이를 통해 개발자는 애플리케이션의 잠재적인 문제를 조기에 발견하고 수정할 수 있습니다.
