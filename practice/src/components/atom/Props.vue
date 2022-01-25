<template>
  <div v-bind="$attrs" class="btn" @click="hey"><slot></slot></div>
</template>
<script>
import { onMounted } from 'vue'

export default {
  name: 'Props',

  inheritAttrs: false,

  props: {
    color: {
      type: String,
      default: 'gray',
    },
  },

  emits: ['hey'],

  setup(props, context) {
    function hey() {
      context.emit('hey')
    }
    onMounted(() => {
      console.log(props.color)
      // props 를 제외한 상속받은 모든 것은  context 로 넘어간다.
      console.log(context.attrs)
    })

    return {
      hey,
    }
  },
}
</script>
