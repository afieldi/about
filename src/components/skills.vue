<template>
<div id="skills" class="exp-background">
  <br><br>
  <div class="container">
    <div class="row">
      <div class="col-sm">
        <exp-section section="languages"/>
        <hr>
      </div>
      <div class="col-sm">
        <exp-section section="libraries" />
        <hr>
        <exp-section section="database" />
      </div>
      <div class="col-sm">
        <exp-section section="cloud" />
        <hr>
        <exp-section section="soft" />
      </div>
    </div>
  </div>
  <!-- <div v-for="i in skills['languages']" :key="i">{{i}}</div> -->
</div>    
</template>

<script>
import expSection from './expsection.vue'
export default {
  components: {
    expSection
  }
}
</script>

<style scoped>
.exp-background {
  height: 100vh;
  background-color: #f2f2f2;
}
hr {
  background-color: black;
}
</style>