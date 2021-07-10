<template>
  <div id="app">
    <PopupDemo />
  </div>
</template>

<script>
// import Slots1 from './examples/slots1/Slots1.vue'
// import TrialModal from './examples/trial_modal/TrialModal.vue'
import PopupDemo from './examples/popup_demo/PopupDemo.vue'

export default {
  name: 'App',
  components: {
    PopupDemo
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
