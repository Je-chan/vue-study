<template>
  <h1 ref="hello">
    Hello Wolrd
  </h1>
  <Liebe ref="liebe"/>
</template>

<script>
import Liebe from './Liebe.vue'
export default {
  name: 'Refs',
  components: {
    Liebe
  },
 
  mounted() {
    console.log(this.$refs.hello.textContent)
    console.log(this.$refs.liebe.$el)
  }
}
</script>