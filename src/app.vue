<template>
  <div id="app">
    <!-- <h1>My Vue App</h1> -->
    <greeter />
    <navbar v-bind:style="navStyle" v-bind:current="'profile'" @openresume="openResume"/>
    <bio @openresume="openResume"/>
    <experience />
    <skills />
    <projects />
    <!-- <exp-bar value="90" /> -->
  </div>
</template>

<script>
import Greeter from './components/welcome.vue'
import Navbar from './components/nav.vue'
import Bio from './components/bio.vue'
import Experience from './components/experience.vue'
import Skills from './components/skills.vue'
import Projects from './components/projects.vue'

export default {
  name: 'zap',
  components: {
    Greeter,
    Navbar,
    Bio,
    Skills,
    Experience,
    Projects
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
    openResume ( ) {
      window.open('https://docs.google.com/document/d/1G8KbbnLW2bxeSr4dgKRv1XnjGX-P8OYZzHf8gV7bKGI/edit?usp=sharing', '_blank');
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