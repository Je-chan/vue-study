<template>
  <div>
    <section v-if='hasFruit'>
      <h1>Fruits</h1>
      <ul>
        <li v-for='fruit in fruits' :key='fruit'>
          {{fruit}}
        </li>
      </ul>
    </section>
    <section>
      <h1>Reversed</h1>
      <ul>
        <li v-for='fruit in reverseFruits' :key='fruit'>
          {{fruit}}
        </li>
      </ul>
    </section>
  </div>
</template>

<script>
export default {
  name: 'Computed',
  data() {
    return {
      fruits: [
      'Apple', 'Banana', 'Cherry'
      ]
    }
  },
  computed: {
    // computed 를 통해서 계산된 데이터를 저장. 
    hasFruit() {
      // this 는 default 다음에 나오는 객체 내부를 의미
      return this.fruits.length > 0
    },
    reverseFruits() {
      return this.fruits.map(fruit => {
        return fruit.split('').reverse().join('')
      })
    }
  }
}
</script>