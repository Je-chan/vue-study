<template>
  <Child />
</template>

<script>  
import Child from './Child.vue'
export default { 
  name: 'Parent',

  components: {
    Child
  },
  
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
