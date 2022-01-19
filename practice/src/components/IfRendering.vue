<template>
<div>
  <p>=== IfRendering ===</p>
  <section>
  <button @click="handler">Click Me!</button>
  <h1 v-if='isShow'>
    Hello?
  </h1>
  <h1 v-else-if='count > 3'>
    클릭 횟수가 3을 넘겼습니다
  </h1>
  <h1 v-else>
    Good!
  </h1>
  </section>
  <!-- template 은 Fragment 처럼 생각하면 됨. 최상위 template 에는 v-if 붙이면 안 된다.-->
  <template v-if='isShow'>
    <h1>Title</h1>
    <h3>하이?</h3>
  </template>
</div>
</template>


<script>
export default {
  name: 'IfRendering',
  data() {
    return {
      isShow: true,
      count: 0
    }
  },
  
  methods: {
    handler() {
      this.isShow = !this.isShow
      this.count += 1
    }
  }
}
</script>
