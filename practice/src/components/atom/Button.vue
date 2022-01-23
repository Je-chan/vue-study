<template>
  <div
    :style="{ backgroundColor: color }" 
    class="btn"
    :class="{large}">
    <!-- Slot 은 컴포넌트도 일반적인 요소 처럼 태그를 열고 닫을 수 있고, 그것을 slot 으로 받을 수 있다.-->
    <slot></slot>
  </div>
</template>

<script>  

export default { 
  name: 'Button',
  props: {
    color: {
      type: String,
      default: 'gray'
    },
    large: {
      type: Boolean,
      default: false
    },
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
