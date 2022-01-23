<template>
  <div class="btn">
    <slot name="icon"></slot>
    <slot name="text"></slot>
  </div>
</template>

<script>  

export default { 
  name: 'Slot',

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
