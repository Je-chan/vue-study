<template>
  <div
    class="btn">
    <!-- Slot 은 컴포넌트도 일반적인 요소 처럼 태그를 열고 닫을 수 있고, 그것을 slot 으로 받을 수 있다.-->
    <slot></slot>
  </div>
  <div 
    class="btn"
    :class="$attrs.class">
    <slot></slot>
  </div>
  <div
    class="btn"
    v-bind="$attrs">
    <slot></slot>
  </div>
</template>

<script>  

export default { 
  name: 'Inherit',
  inheritAttrs: false,
  created() {
    console.log(this.$attrs)
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
    &.je{
      font-size: 1.5rem;
    }
  }
  
</style>
