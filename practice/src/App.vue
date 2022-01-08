<template>
  <div>
    <Lifecycle />
    <Syntax />
    <Computed />
    <Watch />
    <Binding />
  </div>
</template>

<script>  
import Lifecycle from './components/Lifecycle'
import Syntax from './components/Syntax'
import Computed from './components/Computed'
import Watch from './components/Watch'
import Binding from './components/Binding'

export default { 
  
  components: {
    Lifecycle,
    Syntax,
    Computed,
    Watch,
    Binding
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
  p {
    font-size: 2rem;
    color: orange;
    margin-bottom: 1rem;
  }
</style>