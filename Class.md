# 클래스와 스타일 바인딩

## 1. HTML 클래스 바인딩

### HTML 클래스 바인딩

- HTML 클래스 속성에 바인딩을 할 때 객체로 연결할 경우
- v-bind:class 로 클래스를 동적으로 전환할 수 있다.
- 객체의 형태로 여러 속성을 넣을 수 있다.
- 만약 camelCase 가 아니고 특수 기호를 쓴다고 하면 작은 따옴표로 묶어야 한다
- class 로 배열을 넣을 수 있다.

```HTML
<div
  class="static"
  :class"{active: isActive, 'another-class': anohterClass }"
></div>

<!-- 위의 내용은 아래와 같음 -->

<div :class="classObj"></div>

data() {
  return {
    classObkect: {
      activate: true,
      'another-class': flase,
    }
  }
}

<!-- computed 로 계산된 값을 이용할 수 있음 -->

data() {
  return {
    isActive: true,
    error; null
  }
}

computed: {
  classObj() {
    return {
      active: this.isActive && ! this.error,
      'another-class': this.error && this.error.type === 'fatal'
    }
  }

```

<br />
<br />

## 2. 인라인 스타일 바인딩하기

### 객체 구문

- `:style` 객체 구문으로 바인딩할 수 있다.
- 카멜 케이스, 케밥케이스를 사용할 수 있다

```jsx
<div :style="{color: activeColor, 'font-size': fontSize + 'px'}">

data () {
  return {
    activeColor: 'red',
    fontSize: 30
  }
}

// 물론 스타일 객체를 직접 바인딩할 수 있다

<div :style="styleObj"></div>

data () {
  return {
    styleObj: {
      color: 'red',
      fontSize: '13px'
    }
  }
}

```
