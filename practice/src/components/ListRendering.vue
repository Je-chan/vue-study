<template>
<div>
  <p>=== VFor ===</p>
  <section>
  <ul>
    <li
      v-for="(person, index) in people"
      :key="person"
    >
      {{person}}--{{index + 1}}
    </li>
  </ul>
  </section>
  <section>
    <ul>
      <li 
        v-for="{id, name} in hero"
        :key='id'
      >
        {{name}}--{{id}}
      </li>
    </ul>
  </section>
  <button @click="handler">
    Click me!
  </button>
</div>
</template>

<script>
import shortid from 'shortid'

export default {
  name: 'ListRendering',
  data() {
    return {
      people: ['liebe', 'je', 'bono']
    }
  },

  computed: {
    hero () {
      return this.people.map(el  => ({
        id: shortid.generate(),
        name: el
      }))
    }
  },

  methods: {
    handler() {
      this.people.push('Ye')
    }
  }
}
</script>
