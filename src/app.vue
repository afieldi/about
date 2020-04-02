<template>
  <div id="app">
    <!-- <h1>My Vue App</h1> -->
    <greeter />
    <navbar v-bind:style="navStyle" />
    <br><br><br>
    <bio />
    <exp-bar value="90" />
  </div>
</template>

<script>
import Greeter from './components/welcome.vue'
import Navbar from './components/nav.vue'
import Bio from './components/bio.vue'
import ExpBar from './components/expbar.vue'
export default {
  name: 'zap',
  components: {
    Greeter,
    Navbar,
    Bio,
    ExpBar
  },
  data: function() {
    return {
      navStyle: {
        display: "block",
        // top: '100vh'
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