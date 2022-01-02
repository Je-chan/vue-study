<template>
  <div>
    <h1 @click="add">{{ msg }}</h1>
    <h1 v-once @click="add"> {{ msg }} </h1>
    <h1 v-html="content"></h1>
    <h1 :class="'active'">{{ htmlProperty }}</h1>
    <h1 :[attr]="value" @[event]='add'>{{ htmlProperty }}</h1>
  </div>
</template>

<script>  
export default { 
  name: 'Syntax',
  data () {
    return {
      msg: 'Happy New Year', 
      content: '<div style="color: red;">Hello World!!</div>',
      htmlProperty: 'active',
      value: 'active',
      attr: 'class',
      event: 'click'
    }
  },
  methods: {
    add() {
      this.msg += '!'
    }
  }
}
</script>

<style scoped>
  .active {
    color: blue;
    font-size: 2rem;
  }
</style>