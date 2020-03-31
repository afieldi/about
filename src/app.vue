<template>
  <div id="app">
    <navbar v-bind:style="navStyle" />
    <!-- <h1>My Vue App</h1> -->
    <greeter />
  </div>
</template>

<script>
import Greeter from './components/welcome.vue'
import Navbar from './components/nav.vue'
export default {
  name: 'zap',
  components: {
    Greeter,
    Navbar,
  },
  data: function() {
    return {
      navStyle: {
        display: "none"
      }
    }
  }
}
</script>

<style>
#app {
  font-family: Helvetica, Arial, sans-serif;
  color: #2c3e50;
}
</style>