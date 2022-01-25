<template>
  <h1 @click="increase">{{ count }} // {{ doubleCount }}</h1>
  <h1 @click="changeMessage">{{ msg }} / {{ reversedMsg }}</h1>
</template>
<script>
import { ref, computed, watch } from 'vue'
export default {
  setup() {
    const count = ref(0)
    const msg = ref('Hello world!')

    function increase() {
      count.value++
    }

    function changeMsg() {
      msg.value = 'Liebe'
    }

    const dobuleCount = computed(() => {
      return count.value * 2
    })

    const reversedMsg = computed(() => {
      return msg.value.split('').reverse().join('')
    })

    watch(msg, (newValue) => {
      console.log(newValue)
    })

    return {
      count,
      dobuleCount,
      msg,
      reversedMsg,
      increase,
      changeMsg,
    }
  },
}
</script>
<style lang=""></style>
