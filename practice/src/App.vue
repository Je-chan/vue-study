<template>
  <div>
    <Lifecycle />
    <Syntax />
    <Computed />
    <Watch />
    <Binding />
    <IfRendering />
    <ListRendering />
    <EventHandling />
  </div>
</template>

<script>  
import Lifecycle from './components/Lifecycle'
import Syntax from './components/Syntax'
import Computed from './components/Computed'
import Watch from './components/Watch'
import Binding from './components/Binding'
import IfRendering from './components/IfRendering'
import ListRendering from './components/ListRendering'
import EventHandling from './components/EventHandling'

export default { 
  components: {
    Lifecycle,
    Syntax,
    Computed,
    Watch,
    Binding,
    IfRendering,
    ListRendering,
    EventHandling
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
  section {
    margin-top: 1.5rem;
  }
</style>