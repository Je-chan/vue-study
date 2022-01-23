<template>
  <div>
    <p>=== Component ===</p>
    <section>
      <p>=== Component Basic ===</p>
      <Button>Basic</Button>
      <Button color='orange'>Basic</Button>
      <Button 
      :color='color'
      text='Black'><span style='color: red; fontWeight: bold;'>Bare</span></Button>
      <Button large color='royalBlue'>
        Advanced
      </Button>
    </section>
    <section>
      <p>=== Inherit ===</p>
      <Inherit 
      class='je'
      style="color: red; backgroundColor: #000;">
        Inherit
      </Inherit>
    </section>
  </div>
</template>

<script>  
import Button from './atom/Button.vue'
import Inherit from './atom/Inherit.vue'

export default { 
  name: 'ComponentBasic',
  data() {
    return {
      color: '#000'
    }
  },
  components: {
    Button,
    Inherit
  }

}
</script>
