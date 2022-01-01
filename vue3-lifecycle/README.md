# Vue.js 인스턴스와 라이프 사이클

## 1. 어플리케이션 & 컴포넌트 인스턴스

- 모든 vue 어플리케이션은 create 함수를 사용해새로운 어플리케이션 인스턴스를 생성해 시작한다.
- 인스턴스가 생성되면 mount 메소드에 컨테이너를 전달해서 진짜 mount 를 할 수 있다.
- 어플리케이션 인스턴스에 의해 노출된 메소드들은 동일한 인스턴스를 반환해 연결할 수 있다. 즉, 메소드 체이닝이 가능하다

  ```jsx
  Vue.createApp({})
    .component("SearchInput", SearchInputComponent)
    .directive("focus", FocusDirective)
    .use(LocalPlugin);
  ```

## 2. 최상위 컴포넌트

- Root Component 는 우리가 일반적으로 App.vue 를 연결하는 것
- 이 컴포넌트는 어플리케이션을 mount 때 렌더링의 시작점으로 잡는 것
- 컴포넌트들을 여기에 추가적으로 연결해서 사용하는 것

## 3. 라이프사이클 훅

- 각 컴포넌트는 생성될 때 일련의 초기화 단계를 거친다
  - 데이터 관찰
  - 템플릿 컴파일
  - 인스터를 DOM 에 마운트
  - 데이터 변경시 DOM 을 업데이트 (반응성)
- 그 과정에서 라이프사이클 훅이라 불리는 함수도 실행해 사용자가 특정 단계에서 자기 코드를 추가할 수 있다.

<img src='https://v3.ko.vuejs.org/images/lifecycle.svg' alt='라이프사이클 다이어그램'>

> \* 은 중요하게 봐야 하는 메소드

### 1. app = Vue.createApp(options).mount(el)

- createApp 으로 프로젝트를 시작

<br />

### 2. Init events & lifecycle

- 이벤트와 라이프사이클이 초기화 됨

<h3> Method | beforeCreate </h3>

- 잘 사용하지 않음
- 컴포넌트가 생성되기 직전

<br />

### 3. Init injections & reactivity

- 우리가 만들어 놓은 데이터나 기본적인 반응성이 만들어지는 과정
- 만약 go: 4 라는 데이터를 만들었을 때 beforeCreate 에서는 이 데이터를 읽을 수 없다

<br />

<h3> Method | created * </h3>
- 컴포넌트가 생성된 직후

<br />

### 4. HasTemlpate Option?

- Vue.js 옵션으로 template 을 사용하는가?
- 그에 맞는 처리과정을 거침

<br />

<h3> Method | beforeMount </h3>

- html 에 연결되는 마운트 직전에 만들어지는 것

<br />

### 5. Create app.$el and append it to el

- 실제 html 부분에 연결하는 것

<br />

<h3> Method | mounted * </h3>

- html에 연결이 된 직후에 만들어지는 것
- mount 된 직후
- 실제로 화면이 렌더링됐을 때

<br />

### 6. Data changes

- 데이터가 바뀌는 바로 그 시점

<br />

<h3> Method | beforeUpdate </h3>

- 데이터가 변동되고 리렌더링 되기 전에 작동

<br />

### 7. Virtual DOM re-rednered and patch

- 가상 DOM 을 통해 화면에 그려진 내용과 데이터가 변경돼서 화면을 다시 그려야하는 부분을 비교 분석
- 반응성의 개념과 밀접한 부분
- Virtula DOM 을 통해 비교 분석 후 다시 그려야 하는 부분을 캐치한 후 re-render

<br />

<h3> Method | updated </h3>

- update 가 된 후, 즉 데이터가 변경되고 변경된 데이터로 리렌더링 된 직후에 작동하는 메소드

<br />

### 8. app.unmount() is called

- vue.js 로 작성한 컴포넌트와의 연결이 끊어지도록 실행하는 것

<br />

<h3> Method | beforeUnmout </h3>

- 컴포넌트가 끊어지기 직전에 사용되는 메소드

<br />

### 9. unmounted

- 완전히 연결이 끊어졌을 때

<br />

<h3> Method | unmounted </h3>

- 컴포넌트가 끊어졌을 때 사용하는 메소드
