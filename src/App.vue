<template>
  <div id="app">
    <TrialModal />
  </div>
</template>

<script>
// import Slots1 from './examples/slots1/Slots1.vue'
import TrialModal from './examples/trial_modal/TrialModal.vue'

export default {
  name: 'App',
  components: {
    // Slots1
    TrialModal
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
