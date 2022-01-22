<template>
  <div>
    <p>=== KeyModifier ===</p>
    <section>
      <input 
        type="text" 
        @keydown.enter='handler'
        placeholder="Enter"/>
      <input 
        type="text"
        @keydown.ctrl.a='handlerA'
        placeholder="ctrl+A"/>
    </section>
  </div>
</template>

<script>  
export default { 
  name: 'KeyModifier',

  methods: {
    handler(e) {
      // if(e.key === 'Enter') {
      //   console.log('Enter!')
      // }
      console.log('Enter!')
    },
    handlerA (e) {
      
      console.log('Ctrl A')
    }
  }

}
</script>
