<template>
  <div>
    Child: {{msg.value}}
  </div>
</template>

<script>  

export default { 
  name: 'Child',
  inject: ['msg']
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
