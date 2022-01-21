<template>
  <div>
    <p>=== EventHandling ===</p>
    <section>
      <button @click="handler('good', $event)">
        First
      </button>
      <button @click="handler('bad', $event)">
        Second        
      </button>
    </section>
    <section>
      <button @click="handlerA('good'), handlerB('bad')">
        Third
      </button>
      <span>{{thirdGood}}</span>
      <span>{{thirdBad}}</span>
    </section>
  </div>
</template>

<script>  
export default { 
  name: 'EventHandling',
  data () {
    return {
      thirdGood: 'Change me!',
      thirdBad: 'Don\'t Change me!',
    }
  },
  methods: {
    handler(msg, e) {
      console.log(msg, e)
    },
    handlerA(msg) {
      return this.thirdGood = msg
    },
    handlerB(msg) {
      return this.thirdBad = msg
    }
  }

}
</script>
