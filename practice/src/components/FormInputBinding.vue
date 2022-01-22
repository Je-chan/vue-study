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
        v-model="msg2"/>
    </section>
    <section>  
    <h1>{{ checked }}</h1>
      <input 
        type="checkbox"
        v-model="checked"/>
    </section>
    <section>
      <h1>{{ msg3 }}</h1>
      <input 
        type="text"
        @change='msg3 = $event.target.value' />
    </section>
    <section>
      <h1>{{ msg4 }}</h1>
      <input 
        type="text"
        :value='msg4'
        v-model.lazy='msg4' />
    </section>
    <section>
      <h1>{{ msg5 }}</h1>
      <input 
        type="text"
        :value='msg5'
        v-model.number='msg5' />
    </section>
    <section>
      <h1>{{ msg6 }}</h1>
      <input 
        type="text"
        :value='msg6'
        v-model.number="msg6" />
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
      msg3: '@change',
      msg4: 'lazy',
      msg5: 123,
      msg6: 'trim',
      checked: false
    }
  },

  // methods: {
  //   handler(e) {
  //     console.log(e.target.value)
  //     this.msg = e.target.value
  //   }
  // }

  watch: {
    msg5() {
      console.log(typeof this.msg5)
    }
  }
}
</script>
