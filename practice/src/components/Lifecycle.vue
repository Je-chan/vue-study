<template>
    <h1>{{count}}</h1>
</template>

<script>  
export default { 
  name: 'Lifecycle',
  data() {
    return {
      count: 2
    }   
  },
  beforeCreated() {
    console.log('Before created', this.count)
  },
  created() {
    console.log('Created!')
  },
  beforeMount() {
    console.log('Before mount', this.count)
    console.log(document.querySelector('h1')) // null
  },
  mounted() {
    console.log('Mounted')
    console.log(document.querySelector('h1'))
  }
}
</script>
