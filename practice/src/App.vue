<template>
  <div>
    <Lifecycle />
    <Syntax />
    <Computed />
  </div>
</template>

<script>  
import Lifecycle from './components/Lifecycle'
import Syntax from './components/Syntax'
import Computed from './components/Computed'

export default { 
  
  components: {
    Lifecycle,
    Syntax,
    Computed
  }
}
</script>

<style>
  div{
    margin: 2rem 1rem;
  }
  h1 {
    font-size: 2rem;
  }
</style>