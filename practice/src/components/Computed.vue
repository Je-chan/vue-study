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
    <section>
      <button @click='add'>add '?!' </button>
      <h1>Getter : {{reverseTitleMsg}}</h1>
      <h1>{{setterTest}}</h1>
      <h1>{{computedSetter}}</h1>
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
      setterTest: 'Getter and Setter',
      computedSetterTest: 'detupmoc morf retteG',
      fruits: [
      'Apple', 'Banana', 'Cherry'
      ]
    }
  },
  methods: {
    reverseMessage () {
      return this.title.split('').reverse().join('')
    },
    add() {
      this.reverseTitleMsg += '?!'
      // 이건 불가능하다. computed 로 저장한 것은 읽기 전용이기 때문
      // Getter : 값을 가져오는 방식으로만 사용하는 것.
      this.setterTest += '?!'
      // 반면에 data 로 저장된 것은 setter 까지 포함이 된다. 
      this.computedSetter += '?!'
      // computed 도 getter 와 setter 둘 다 사용할 수 있다.
      // get() 을 통해서 값을 가져오는 거고
      // set() 을 통해서 값을 변형시킬 때 실행될 함수를 만드는 것
      // 여기에서 ?! 를 추가하고 그게 set(newValue) 의 newValue 값으로 들어가게 된디.
      // 그렇게 set 함수가 실행된 다음에 화면에 렌더링할 때는 get() 의 내용에 따라 실행
      // 많이 쓰이지는 않지만 Vuex 라는 중앙 집중식 저장소를 사용할 때 유용하게 사용할 수 있다.
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
    },
    computedSetter: {
      get() {
        return this.computedSetterTest.split('').reverse().join('')
      }, 
      set(newValue) {
        this.computedSetterTest = newValue
      }
    }
  }
}
</script>

<style scoped>
  section {
    margin: 1rem 0;
  }
</style>