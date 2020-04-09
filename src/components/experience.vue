<template>
  <div class="exp-background" id="experience">
    <br>
    <div class="container">
      <h1 class="text-center">
        Experience
      </h1>
      <hr>
      <exp-item v-for="expj in expJson['work']" :key="expj.displayName" v-bind:expObj="expj"/>
    </div>
  </div>
</template>

<script>
import ExpItem from './experienceitem'
import ExpJson from '../assets/json/experience.json'
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