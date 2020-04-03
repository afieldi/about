<template>
  <div>
    <h3>{{skillName}}</h3>
    <div v-for="skill in skills" :key="skill.displayName">
      <h5>{{skill.displayName}}</h5>
      <exp-bar v-bind:value="skill.value" />
    </div>
  </div>
</template>

<script>
import expBar from './expbar.vue'
import skillsJson from '../assets/skills.json'

export default {
  props: [
    "section"
  ],
  data: function ( ) {
    return {
      skills: skillsJson[this.section]["data"],
      skillName: skillsJson[this.section]["displayName"]
    }
  },
  components: {
    expBar
  }
}
</script>

<style scoped>
  h5 {
    margin: 0;
  }
</style>