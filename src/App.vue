<template>
  <div id="app">
    <Sanduiches></Sanduiches>
  </div>
</template>

<script>
import Sanduiches from './components/Sanduiches.vue'

export default {
  name: 'App',
  components: { Sanduiches }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>

