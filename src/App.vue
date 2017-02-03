<template>
  <div id="app">
  <carselect></carselect>
</template>

<script>
import Carselect from './steps/Carselect'

export default {
  name: 'app',
  components: {
    Carselect
  },
  data: function () {
    return {
      age: 3
    }
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
