<template>
  <div id="app">
    <!-- <h1>My Vue App</h1> -->
    <greeter />
    <navbar v-bind:style="navStyle" v-bind:current="'profile'"/>
    <bio />
    <experience />
    <skills />
    <!-- <exp-bar value="90" /> -->
  </div>
</template>

<script>
import Greeter from './components/welcome.vue'
import Navbar from './components/nav.vue'
import Bio from './components/bio.vue'
import Experience from './components/experience.vue'
import Skills from './components/skills.vue'

export default {
  name: 'zap',
  components: {
    Greeter,
    Navbar,
    Bio,
    Skills,
    Experience
  },
  data: function() {
    return {
      navStyle: {
        display: "block",
      }
    }
  },
  created: function ( ) {
    window.addEventListener('scroll', this.navCheck);
  },
  methods: {
    navCheck: function ( event ) {
      // switch (window.pageYOffset) {
      //   case value:
          
      //     break;
      
      //   default:
      //     break;
      // }
      // console.log ( window.pageYOffset)
    }
  }
}
</script>

<style>
#app {
  font-family: Helvetica, Arial, sans-serif;
  color: #2c3e50;
}

.bg-dark { 
  background-color: #360707 !important;
}
</style>