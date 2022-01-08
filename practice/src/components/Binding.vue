<template>
  <div>
    <p>=== Class ===</p>
    <h1 
      :class="{active: isActive}"
      @click="activate"
    >
      Class({{isActive}})
    </h1>
    <h1
      :style="{color, 'font-size': fontSize}"
      @click="chnageStyle"
    >
      Style
    </h1>
    <h1
      :style="[fontStyle, backgroundStyle]"
      @click="changeFontStyle"
    >
      Style 객체 바인딩
    </h1>
  </div>
</template>

<script>  
export default { 
  name: 'Binding',
  data() {
    return {
      isActive: false,
      color: 'red',
      fontSize: '1.5rem',
      fontStyle: {
        color: 'green',
        fontSize: '1.5rem'
      },
      backgroundStyle: {
        backgroundColor: '#eee',
      }
    }
  },

  methods: {
    activate() {
      this.isActive = !this.isActive
    },
    chnageStyle() {
      this.color='blue'
      this.fontSize = '2rem'
    },
    changeFontStyle() {
      this.fontStyle.color='purple'
      this.fontStyle.fontSize = '2rem'
    }
  }
}
</script>

<style scoped>
  h1 {
    width: 15rem;
  }
  .active {
    color: red;
    font-weight: bold;
  }

</style>