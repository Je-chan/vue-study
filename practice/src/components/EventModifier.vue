<template>
  <div>
    <p>=== EventModifier ===</p>
    <section>
      <a 
        href="https://naver.com"
        target='_blank'
        @click='handler'>
        NAVER
      </a>
    </section>
    <section>
      <!-- .prevent 수식어를 써도 위와 똑같은 결과를 가져온다 -->
      <a 
        href="https://naver.com"
        target='_blank'
        @click.prevent='handlerA'>
        NAVER / @click.prevent
      </a>
    </section>
    <section>
      <!-- .once 는 단 한 번만 실행하고 그 다음에 또 이벤트가 실행되더라도 핸들러라는 메소드는 실행되지 않는다 -->
      <a 
        href="https://naver.com"
        target='_blank'
        @click.once='handlerB'>
        NAVER / @click.once
      </a>
    </section>  
    <section>
      <!-- 기존에 D 박스를 누르면 C 박스의 이벤트도 눌리지만 .stop 을 이용해 방지할 수 있다 -->
      <div 
        class='parent'
        @click='handlerC'
        @wheel='handlerX'>
        C
        <div
          class='child'
          @click='handlerD'>
          Origin
        </div>
        <div 
          class='child stop'
          @click.stop='handlerE'>
          stop
        </div>
        <div
          class='child capture'
          @click.capture='handlerF'>
          capture
          <div
            @click='handlerG'>
            G
          </div>
        </div>
        <div
          class='child self'
          @click.self.stop='handlerH'>
          self
          <div>
            H
          </div>
        </div>
        <div
          class='longChild'>
          longChild  
        </div>
      </div>
    </section>  
  </div>
</template>

<script>  
export default { 
  name: 'EventModifier',

  methods: {
    handler(e) {
      // preventDefault 는 기본 동작을 방지하는 것을 의미한다
      // a 태그를 눌렀을 때 다음 페이지로 넘어가는 것은 기본 동작이지 우리가 직접 구현한 것은 아님
      // Default 로 존재하는 동작을 prevent 하는 의미한다.
      e.preventDefault();
      console.log('눌렸다')
    },
    handlerA() {
      console.log('A 눌렸다')
    },
    handlerB() {
      console.log('B 눌렸다')
    },
    handlerC() {
      console.log('C 눌렸다')
    },
    handlerD() {
      console.log('origin')
    },
    handlerE() {
      console.log('stop')
    },
    handlerF(e) {
      console.log('capture')
      console.log(e.target)
      console.log(e.currentTarget)
    },
    handlerG() {
      console.log('G 눌렸다')
    },
    handlerH(e) {
      console.log('self')
      console.log(e.target)
      console.log(e.currentTarget)
    },
    handlerX() {
      // 밑의 주석을 풀면 렉이 걸릴 수 있으므로 주석처리
      // for(let i = 0 ; i < 10000 ; i++) {
      //   console.log('1')
      // }
    }
  }

}
</script>

<style scoped lang='scss'>
  .parent {
    position: relative;
    width: 10rem;
    height: 15rem;
    color: #fff;
    background-color: #000;
    padding: 1rem;
    overflow: auto;
    .child {
      width: 3rem;
      height: 2rem;
      color: #000;
      padding: .3rem;
      background-color: #fff;
    }
    .stop {
      position: absolute;
      top: 0;
      right: 3px;
    }
    .capture {
      position: absolute;
      top: 4rem;
      height: 3rem;
      right: 3px;
      div {
        position: absolute;
        top: 0;
        background-color: #000; 
        color: #fff;
        width: 2rem;
        height: 1.3rem;
      }
    }
    .self {
      position: relative;
      height: 3rem;
      right: 3px;
      div {
        position: absolute;
        top: 0;
        background-color: #000; 
        color: #fff;
        width: 2rem;
        height: 1.3rem;
      }
    }
    .longChild {
      width: 5rem;
      height: 15rem;
      color: #000;
      padding: .3rem;
      background-color: #fff;
    }
  }
</style>