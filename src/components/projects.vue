<template>
  <div class="projects-bg" id="projects">
    <br>
    <div class="container">
      <h1 class="text-center">
        Projects
      </h1>
      <hr>
      <!-- <div class="row">
        <div class="col" v-for="(projCol, index) in projArr" :key="index">
          <div v-for="proj in projCol" :key="proj.displayName" class="card bg-dark text-white proj-card" v-on:click="toggleSlide(proj.displayName)">
            <img class="card-img"
                v-bind:src="require('@/assets/images/' + proj.image)"
                alt="Card image"
                >
            <div class="card-img-overlay">
              <h3 class="card-title" v-bind:class="getColorClasses(proj.theme)">{{proj.displayName}}</h3>
            </div>
            <div v-bind:id="proj.displayName + '-desc'" v-bind:class="[proj.theme === 'dark' ? 'card-dark' : 'card-light']" class="card-desc card-hidden" >
              <div class="container">
                <a v-bind:href="proj.link" class="text-primary"><i>View Project</i></a>
                <p>{{proj.shortDescription}}</p>
                <hr v-bind:class="[proj.theme === 'dark' ? 'bg-light' : 'bg-dark']">
                <div>
                  <bubble v-for="skillItem in proj.skills" :key="skillItem" :skill="skillItem"></bubble>
                </div>
                <br>
              </div>
            </div>
          </div>
        </div>
      </div> -->
      <div v-for="(proj, index) in projJson" :key="index">
        <p>
          <a class="btn btn-dark project-button" data-toggle="collapse" v-bind:href="'#project-' + index" role="button" aria-expanded="false" v-bind:aria-controls="'project-' + index">
            {{proj.displayName}}: <a class="subText">{{proj.startDate}}</a>
          </a>
        </p>
        <div class="collapse" v-bind:id="'project-' + index">
          <div class="card card-body">
            <div class="row">
              <div class="col-md-4">
                <div class="card" style="width: 18rem;">
                  <img class="card-img-top" v-bind:src="require('@/assets/images/' + proj.image)" alt="Project Image">
                  <div class="card-body">
                    <!-- <h5 class="card-title"></h5> -->
                    <p class="card-text">{{proj.shortDescription}}</p>
                    <a v-bind:href="proj.link" class="btn btn-danger go-to-button">Go to project</a>
                  </div>
                </div>
              </div>
              <div class="col">
                <div class="card-title"><h2>{{proj.displayName}}</h2></div>
                <hr>
                <div v-html="proj.longDescription">
                  
                </div>
                <hr>
                <div>
                  <bubble v-for="skillItem in proj.skills" :key="skillItem" :skill="skillItem"></bubble>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import projJson from '../assets/json/projects.json'
import bubble from './skillbubble'

let projArr = [];

export default {
  data: function ( ) {
    return {
      projJson: projJson["projects"],
      projArr: projArr
    }
  },
  components: {
    bubble
  },
  created: function ( ) { 
    let cols = 0;
    console.log(window.innerWidth);
    if (window.innerWidth > 1200) {
      cols = 3;
    }
    else if (window.innerWidth > 700) {
      cols = 2;
    }
    else {
      cols = 1;
    }

    let perCol = Number(projJson["projects"].length / cols);
    
    for (var i = 0; i < cols; i ++) {
      projArr.push(projJson["projects"].slice(i * perCol, (i * perCol) + perCol));
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

.proj-card {
  margin-bottom: 15px;
}

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
  transition: 0.5s;
  max-height: 30em;
  overflow: hidden;
  position: relative;

}

.card-dark {
  background-color: rgb(36, 36, 36);
  color: #f2f2f2;
}

.card-light {
  background-color: rgb(219, 214, 214);
  color: black;
}

.card-hidden { 
  max-height: 0;
}

.projects-bg {
  background-color: #f2f2f2;
}

.card-title {
  text-align: center;
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

.project-button {
  width: 100%;
  text-align: left;
  font-size: 1.2em;
}

.go-to-button {
  width: 100%;
  text-align: center;
}

.subText {
  font-style: italic;
  font-size: 0.8em;
}
</style>