<template>
  <div class="btn">
    <slot></slot>
  </div>
  <h1 @click="$emit('je')">EMIT</h1>
  <!-- dblclick 은 더블 클릭을 의미함 -->
  <!-- $emit 의 첫 번째 인자에는 어떤 메소드를 실행시킬지고 두 번째 인자는 그 메소드의 인자로 넘겨줄 것을 넣어주게 된다-->
  <h1 @dblclick="$emit('je', $event)">DOUBLE</h1>
  <input 
    type="text"
    v-model="msg" />
</template>

<script>  

export default { 
  name: 'Emit',
  emits: [
    'je',
    'chnageMsg'
  ],
  data () {
    return {
      msg: ''
    }
  },
  watch: {
    msg() {
      this.$emit('changeMsg', this.msg)
    }
  }
}
</script>


<style scoped lang="scss">
  .btn {
    display: inline-block;
    margin: 0rem;
    padding: .5rem 1rem;
    border-radius: 4px;
    background-color: gray;
    color: #fff;
    cursor: pointer;
    &.large {
      font-size: 1.5rem;
    }
  }
  
</style>
