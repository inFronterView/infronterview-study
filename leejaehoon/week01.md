# 목차

- JavaScript
  - [EcmaScript와 JavaScript의 차이점은 무엇인가요?](#ecmascript와-javascript의-차이점은-무엇인가요)
  - [JavaScript의 자료형(타입)에는 어떤 것들이 있나요?](#javascript의-자료형타입에는-어떤-것들이-있나요)
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

> `EcmaScript`는 `JavaScript`의 핵심 기능과 문법을 정의한 표준 규격입니다.<br/> > `JavaScript`는 실제 실행 환경에서 동작하는 언어로 `EcmaScript`의 사양을 지켜 구현되었습니다.<br/> > `JavaScript`는 `EcmaScript`의 사양을 준수하여 구현된 언어로 브라우저 API와 같은 자체적인 구현과 확장 또한 가지고 있습니다.<br/>

<br/>

## JavaScript의 자료형(타입)에는 어떤 것들이 있나요?

> `JavaScript`의 자료형에는 원시 타입과 객체 타입이 존재합니다.<br/>
> 원시 타입은 값 자체를 변수에 저장해 불변성을 가지지만, 객체 타입은 값이 저장된 주소를 변수에 저장하기 때문에 변경 가능합니다.<br/>

<br/>

## Document Object Model이란 무엇인가요?

> DOM은 웹 문서를 프로그래밍적으로 조작할 수 있는 인터페이스입니다.<br/>
> HTML이나 XML 문서를 트리 구조의 객체 모델로 표현하여, JavaScript 같은 언어로 동적으로 내용, 구조, 스타일을 변경할 수 있게 해줍니다.<br/>

<br/>

## 이벤트 위임이란 무엇인가요? 이벤트 캡쳐링과 이벤트 버블링의 차이점은 무엇인가요?

> 이벤트 위임은 이벤트 버블링을 통해 하위 요소들의 이벤트를 공통 조상 요소에서 처리하는 기법입니다.<br/>
> 이벤트 캡처링은 DOM 트리의 최상위 요소에서 이벤트 타겟으로 내려가는 과정이고,<br/>
> 이벤트 버블링은 이벤트 타겟에서 DOM 트리를 따라 최상위로 올라가는 과정입니다.<br/>

<br/>

## event.target과 event.currentTarget의 차이점에 대해 설명해보세요.

> `event.target` 은 이벤트가 실제로 발생한 요소를 가리키고<br/> > `event.currentTarget` 은 현재 동작중인 이벤트 핸들러가 부착된 요소를 가리킨다.<br/>
> 이벤트 버블링 과정에서 `event.target` 이 가리키는 요소는 변하지 않지만<br/> > `event.currentTarget` 이 가리키는 요소는 이벤트가 버블링되면서 부모 요소의 이벤트 핸들러가 실행될 때마다 변경된다.<br/>

<br/>

## Call by value와 Call by reference의 차이점은 무엇인가요?

> `Call by value`는 함수에 값의 복사본을 전달하여 원본 데이터를 보호하는 반면,<br/> > `Call by reference`는 메모리 주소를 전달하여 원본 데이터를 직접 조작할 수 있게 합니다.<br/>
> 이 차이는 함수 내에서 변수를 수정할 때 원본 데이터의 변경 여부를 결정짓는 핵심 요소입니다.<br/>

<br/><br/>

# React

## 브라우저에 URL을 입력한 순간부터 화면에 웹 페이지가 나타나기까지의 모든 과정을 아는대로 최대한 자세히 설명해보세요.

> 브라우저는 HTML을 파싱하여 DOM을 구축하고, CSS를 파싱하여 CSSOM을 생성합니다.<br/>
> 이후 JavaScript 파일을 다운로드해 로드되면 HTML 파싱을 중단시키고 즉시 실행됩니다.<br/> > `defer` 속성이 있으면 HTML 파싱이 완료된 후 실행됩니다.<br/>
> 이 과정을 통해 웹 페이지가 렌더링됩니다.<br/>

<br/>

## package.json, package-lock.json, node_modules는 무엇인가요?

> `package.json`은 프로젝트의 메타데이터와 의존성을 정의하는 설정 파일이고,
> `package-lock.json`은 정확한 버전 정보를 포함한 의존성 트리를 관리합니다.
> `node_modules`는 이러한 의존성 패키지들이 실제로 설치되는 디렉토리로, `npm`이나 `yarn` 같은
> 패키지 관리자에 의해 관리됩니다.

<br/>

## Client Side Rendering이란 무엇인가요?

> **Client Side Rendering**은 사용자의 브라우저에서 웹 페이지의 UI를 동적으로 생성하는 방식입니다.<br/>
> 초기 로딩 후에는 빠른 페이지 전환과 풍부한 사용자 경험을 제공하지만, 초기 로딩 시간이 길어질 수 있습니다.<br/>

<br/>

## Single Page Application이란 무엇인가요?

> **Single Page Application**는 초기 로딩 후 페이지 전체를 다시 로드하지 않고 필요한 데이터만 비동기적으로 가져와 클라이언트 측에서 동적으로 렌더링합니다.<br/>
> React나 Vue.js 와 같은 JavaScript 프레임워크를 활용해 구현됩니다.<br/>

<br/>

## 상태 변화에 대해 React는 어떻게 반응할까요?

> React에서 상태 변화가 발생하면, 내부 큐에 변경사항을 모아 배치 처리해 가상 DOM을 생성합니다.<br/>
> 디핑 알고리즘을 통해 이전 가상 DOM과 비교해 변경사항만 실제 DOM 에 적용합니다.<br/>
> 이 과정에서 불필요한 리렌더링을 방지하고 실제 DOM 조작을 최소화하여 성능을 최적화합니다.<br/>

<br/>

## 리액트의 Strict Mode는 어떤 역할을 하는 것인지 최대한 자세히 설명해보세요.

> React의 Strict Mode는 개발 과정에서 잠재적인 문제를 조기에 발견하기 위한 도구입니다.<br/>
> 이는 컴포넌트의 두 번 렌더링하여 같은 입력값에 같은 결과를 만들어내는지 감지합니다.<br/>
> Strict Mode는 순수 컴포넌트를 작성하도록 해 안정성과 유지보수성을 향상시킬 수 있습니다.<br/>
