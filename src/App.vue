<template>
  <div id="app">
    <main-screen />
  </div>
</template>

<script>
import MainScreen from './components/MainScreen.vue'

export default {
  name: 'app',
  components: {
    MainScreen
  }
}
</script>

<style lang="scss">
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
