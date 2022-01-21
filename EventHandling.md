# 이벤트 핸들링

## 1. v-on

- @ 를 사용해서 DOM 이벤트를 듣고 트리거될 때와 자바 스크립트를 시랳앟ㄹ 때 사용한다

```html
<div id="basic-event">
  <button @click="counter +=1">Add 1</button>
  <p>{{counter}} 만큼 눌렸습니다</p>
  <p></p>
</div>
```

```javascript
Vue.createApp({
  data() {
    return {
      counter: 0,
    }
  },
}).mount('#basic-event')
```

## 2. 메소드 이벤트 핸들러

- javascript 이벤트 핸들링 로직 자체를 v-on 속성으로 넣는 일은 간단하지 않는다
- 그래서 웬만하면 methods 에 실행할 이벤트 로직을 작성해서 넣어주는 것이 좋다. 즉
