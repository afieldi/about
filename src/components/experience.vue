<template>
  <div class="exp-background" id="experience">
    <br><br><br>
    <div class="container">
      <exp-item v-for="expj in expJson['work']" :key="expj.displayName" v-bind:expObj="expj"/>
    </div>
  </div>
</template>

<script>
import ExpItem from './experienceitem'
import ExpJson from '../assets/experience.json'
export default {
  components: {
    ExpItem
  },
  data: function ( ) {
    return {
      expJson: ExpJson
    }
  }
}
</script>

<style scoped>
.exp-background {
  background-color: #f2f2f2;
}
</style>