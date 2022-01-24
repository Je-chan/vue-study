<template>
  <div>
    <p>=== Component ===</p>
    <section>
      <p>=== Component Basic ===</p>
      <Button>Basic</Button>
      <Button color='orange'>Basic</Button>
      <Button 
      :color='color'
      text='Black'><span style='color: red; fontWeight: bold;'>Bare</span></Button>
      <Button large color='royalBlue'>
        Advanced
      </Button>
    </section>
    <section>
      <p>=== Emit ===</p>
      <!-- Vue 에서는 이벤트를 명시할 때 카멜 케이스가 아닌 케밥 케이스를 사용한다 -->
      <Emit
        @je='log'
        @change-msg="logMsg">
        Emit
      </Emit>
    </section>
    <section>
      <p>=== Slot ===</p>
      <Slot>
        <!-- v-slot 은 #으로 약어 사용할 수 있다 -->
        <template #text>
          <span>Slot</span>
        </template>
        <template v-slot:icon>
          <span> (A) </span>
        </template>
      </Slot>
    </section>
    <section>
      <p>=== Provide and Inject ===</p>
      <button @click="message = 'Liebe'">
        Change
      </button>
      <h1>App: {{message}} </h1>
      <Parent />
    </section>
    <section>
      <p>=== Refs ===</p>
      <Refs />
    </section>
  </div>
</template>

<script>  
import Button from './atom/Button.vue'
import Inherit from './atom/Inherit.vue'
import Emit from './atom/Emit.vue'
import Slot from './atom/Slot.vue'
import Parent from './atom/Parent.vue'
import {computed} from 'vue'
import Refs from './atom/Refs.vue'

export default { 
  name: 'ComponentBasic',
  data() {
    return {
      color: '#000',
      message: 'Hello World!'
    }
  },

  components: {
    Button,
    Inherit,
    Emit,
    Slot,
    Parent,
    Refs
  },

  methods: {
    log() {
      console.log('Click')
    },
    logMsg(msg) {
      console.log(msg)
    }
  },

  provide() {
    return {
      msg: computed(() => {
        return this.message
      })
    }
  },

}
</script>
