<template lang="">
  <h1 @click="increase">
    {{count}} / {{ tripleCount}}
  </h1>
  <h1>
    {{ msg }} / {{ reversedMsg }}
  </h1>
</template>

<script>

import {ref, computed} from 'vue'

export default {
  // ! 기존 Vue.2
  // data() {
  //   return {
  //     msg: 'Hey!',
  //     count: 0,
  //   }
  // },

  // computed: {
  //   tripleCount() {
  //     return this.count * 3
  //   },
  //   reversedMessage() {
  //     return this.msg.split('').reverse().join('')
  //   }
  // },

  // methods: {
  //   increase() {
  //     this.count++
  //   }
  //}

  // ! Vue.3 
  setup() {
    const msg = ref('Hello World!')
    const reversedMsg = computed(() => {
      return msg.value.split('').reverse().join('')
    })

    const count = ref(0)
    const tripleCount = computed(() => count.value * 3)

    const increase = () => {
      count.value++
    }

    return {
      msg,
      reversedMsg,
      count,
      tripleCount,
      increase
    }

  }
}
</script>
