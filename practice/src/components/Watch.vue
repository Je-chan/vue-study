<template>
  <div>
    <p>=== Watch ===</p>
    <h1 @click="changeMessage">{{msg}}</h1>
    <h1>{{reversedMsg}}</h1>
  </div>
</template>

<script>  
export default { 
  name: 'Watch',
  data() {
    return {
      msg: 'Here, message'
    }
  },

  computed: {
    reversedMsg() {
      return this.msg.split('').reverse().join('')
    }
  },

  watch: {
    msg() {
      console.log('msg: ', this.msg)
    },

    reversedMsg(changedValue) {
      console.log('reversedMsg: ', changedValue)
    }
  },

  methods: {
    changeMessage() {
      this.msg = 'Good!'
    }
  }
}
</script>
