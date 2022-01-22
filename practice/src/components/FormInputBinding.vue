<template>
  <div>
    <p>=== FormInputBinding ===</p>
    <section>
      <h1>{{ msg }}</h1>
      <!-- @input 은 실제 인풋 창에 데이터가 하나씩 들어갈 때마다 실행되는 이벤트 -->
      <input 
        type="text"
        :value='msg'
        @input='msg = $event.target.value'/>
    </section>
    <section>
      <h1>{{ msg2 }}</h1>
      <input 
        type="text"
        :value='msg2'
        v-model='msg2'/>
    </section>
    <section>  
    <h1>{{ checked }}</h1>
      <input 
        type="checkbox"
        v-model='checked'/>
    </section>
  </div>
</template>

<script>  
export default { 
  name: 'FormInputBinding',
  data () {
    return {
      msg: '$event',
      msg2: 'v-model',
      checked: false
    }
  },

  // methods: {
  //   handler(e) {
  //     console.log(e.target.value)
  //     this.msg = e.target.value
  //   }
  // }
}
</script>
