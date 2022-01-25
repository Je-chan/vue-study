<template>
  <div>
    <Lifecycle />
    <Syntax />
    <Computed />
    <Watch />
    <Binding />
    <IfRendering />
    <ListRendering />
    <EventListener />
    <EventModifier />
    <KeyModifier />
    <FormInputBinding />
    <ComponentBasic />
    <CompositionInit />
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
import EventListener from './components/EventListener'
import EventModifier from './components/EventModifier'
import KeyModifier from './components/KeyModifier'
import FormInputBinding from './components/FormInputBinding'
import ComponentBasic from './components/ComponentBasic'
import CompositionInit from './components/CompositionInit'

export default { 
  components: {
    Lifecycle,
    Syntax,
    Computed,
    Watch,
    Binding,
    IfRendering,
    ListRendering,
    EventListener,
    EventModifier,
    KeyModifier,
    FormInputBinding,
    ComponentBasic,
    CompositionInit
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