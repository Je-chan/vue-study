<template>
  <div>
    <section v-if='hasFruit'>
      <!--이렇게 하면 아쉬운 점은 같은 로직인데 세 번 로직이 실행된다는 점 -->
      <h1>{{ reverseMessage() }}</h1>
      <h1>{{ reverseMessage() }}</h1>
      <h1>{{ reverseMessage() }}</h1>
      <ul>
        <li v-for='fruit in fruits' :key='fruit'>
          {{fruit}}
        </li>
      </ul>
    </section>
    <section>
      <!-- computed 를 사용해 값을 캐싱해서 사용할 수 있음. computed 에 저장될 때 로직이 딱 한 번만 실행된다. -->
      <h1>{{reverseTitleMsg}}</h1>
      <h1>{{reverseTitleMsg}}</h1>
      <h1>{{reverseTitleMsg}}</h1>
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
      title: 'stiurF',
      reversedTitle: 'Fruits',
      fruits: [
      'Apple', 'Banana', 'Cherry'
      ]
    }
  },
  methods: {
    reverseMessage () {
      return this.title.split('').reverse().join('')
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
    },
    reverseTitleMsg () {
      return this.reversedTitle.split('').reverse().join('')
    }
  }
}
</script>

<style scoped>
  section {
    margin: 1rem 0;
  }
</style>