<template>
  <div id="profile" class="container small-container">
    <div class="row">
      <div class="col-sm">
        <img src="../assets/nebi-profile.jpg" alt="" class="rounded-circle nebi-pic">
        <p>
          I am embarressed to write about my self so instead here is a blurb about my cat. Her name is Nebi - she likes
          to lay around all day with the occasional spurt of exercise. She'll meow at you to get her to play with you then 
          promptly lie down after two minutes deciding that play time is over. 
        </p>
      </div>
      <div class="col-sm-4">
        <div>
          <b>Location</b>
          <p>Mississauga, Ontario <br> Canada</p>
          <b>Email</b>
          <p>arek.fielding@gmail.com</p>
          <button type="button" class="full-button btn btn-dark">View Resume</button>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
module.exports = {
  props: [
    "child-comp"
  ]
}
</script>

<style scoped>

@media (min-width: 600px) {
  .full-button {
    width: 80%;
    left: 10%;
    height: 3em;
    position: relative;
  }
  .nebi-pic {
    width: 125px;
    float: right;
    margin: 15px;
  }
  .small-container {
    width: 50%;
    min-width: 500px;
  }

}

@media (max-width: 599px) {
  .nebi-pic {
    width: 70%;
    left: 15%;
    position: relative;
  }
}
</style>