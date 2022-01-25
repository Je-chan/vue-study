<template>
  <Props class="je" style="colorL red" color="#ff000" @hey="log">
    It's Me
  </Props>
</template>
<script>
import Props from '../atom/Props.vue'
export default {
  components: {
    Props,
  },
  methods: {
    log() {
      console.log('Hey!')
    },
  },
}
</script>
