<template>
  <div class="projects-bg">
    <br><br><br>
    <div class="container">
      <div class="card-columns">
        <div v-for="i in 9" :key="i" class="card bg-dark text-white">
          <img class="card-img" src="https://encrypted-tbn0.gstatic.com/images?q=tbn%3AANd9GcTqEn5J68S37GHH43u0WqC-yswafV8jk60Z4_cccPitDzoT0lA5&usqp=CAU" alt="Card image">
          <div class="card-img-overlay">
            <h5 class="card-title text-center vertical-center">Card title</h5>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import projJson from '../assets/json/projects.json'

export default {

}
</script>

<style scoped>
.projects-bg {
  background-color: #f2f2f2;
}

.vertical-center {
  position: relative;
  top: 50%;
  transform: translateY(-50%);
}

@media (min-width: 1200px) {
  .card-columns {
    column-count: 5;
  }
  
}
</style>