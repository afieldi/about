<template>
  <div class="projects-bg" id="projects">
    <br>
    <div class="container">
      <h1 class="text-center">
        Projects
      </h1>
      <hr>
      <div class="card-columns">
        <div v-for="proj in projJson" :key="proj.displayName" class="card bg-dark text-white" v-on:click="toggleSlide(proj.displayName)">
          <img class="card-img"
               v-bind:src="require('@/assets/images/' + proj.image)"
               alt="Card image"
               >
          <div class="card-img-overlay">
            <h3 class="card-title" v-bind:class="getColorClasses(proj.theme)">{{proj.displayName}}</h3>
          </div>
          <div v-bind:id="proj.displayName + '-desc'" class="card-desc card-hidden bg-secondary text-light">
            <div class="container">
              <a v-bind:href="proj.link" class="text-light"><i>View Project</i></a>
              <!-- <hr> -->
              <p>{{proj.shortDescription}}</p>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import projJson from '../assets/json/projects.json'

export default {
  data: function ( ) {
    return {
      projJson: projJson["projects"]
    }
  },
  methods: {
    toggleSlide: function ( projName ) {
      var e = document.getElementById(projName + "-desc");
      e.classList.toggle ( "card-hidden" );
    },
    getColorClasses: function ( scheme ) {
      if ( 'dark' === scheme ) {
        return [
          "text-light",
        ]
      }
      else if ( 'light' === scheme ) {
        return [
          "text-dark"
        ]
      }
    }
  }
}
</script>

<style scoped>

.card-img { 
  transition: 0.4s;
}

.card:hover { 
  cursor: pointer;
}

.card:hover .card-img {
  filter: blur(3px);
}

.card-desc { 
  /* background-color: rgb(236, 208, 208); */
  color: black;
  transition: 0.5s;
  max-height: 30em;
  overflow: hidden;
  position: relative;
}

.card-hidden { 
  max-height: 0;
}

.projects-bg {
  background-color: #f2f2f2;
}

.vertical-center {
  position: relative;
  /* top: 50%;
  transform: translateY(-50%); */
}

/* @media (min-width: 1200px) {
  .card-columns {
    column-count: 5;
  } 
} */
</style>