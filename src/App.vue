<template>
  <div id="app">
    <Slots1 />
  </div>
</template>

<script>
import Slots1 from './examples/slots1/Slots1.vue'

export default {
  name: 'App',
  components: {
    Slots1
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
