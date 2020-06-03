<template>
<div id="skills" class="skills-background">
  <br>
  <div class="container">
    <h1 class="text-center">
      Skills
    </h1>
    <hr>
    <div class="row">
      <div class="col-sm">
        <skill-section section="languages"/>
        <hr>
        <skill-section section="soft" />
      </div>
      <div class="col-sm">
        <skill-section section="cloud" />
        <hr>
        <skill-section section="libraries" />
        <hr>
        <skill-section section="database" />
      </div>
    </div>
  </div>
  <br><br>
  <!-- <div v-for="i in skills['languages']" :key="i">{{i}}</div> -->
</div>    
</template>

<script>
import SkillSection from './skillsection.vue'
export default {
  components: {
    SkillSection
  }
}
</script>

<style scoped>
.skills-background {
  /* height: 100vh;
  background-color: #f2f2f2; */
}
hr {
  background-color: black;
}
</style>