<template>
  <div id="profile" class="container small-container">
    <br>
    <h1 class="text-center">
      About
    </h1>
    <hr>
    <div class="row">
      <div class="col-sm">
        <img src="../assets/images/nebi-profile.jpg" alt="" class="rounded-circle nebi-pic">
        <p>
          I am a Fullstack Software Developer experienced in both front and back end development. I have previously 
          worked with some of the most popular backend server technologies such as Java (SpringBoot), Nodejs (Express), 
          and Python (Django, Flask). My career has also seen me work with many of the currently popular front-end Single 
          Page Application frameworks such as Vue.Js, Angular, and React.
        </p>
      </div>
      <div class="col-sm-4" style="text-align: center;">
        <div>
          <b>Location</b>
          <p>Mississauga, Ontario <br> Canada</p>
          <b>Email</b>
          <p>arek.fielding@gmail.com</p>
          <button type="button" class="full-button btn btn-dark" v-on:click="$emit('openresume')">View Resume</button>
        </div>
      </div>
    </div>
    <br>
  </div>
</template>

<script>
module.exports = {
  props: [
    "child-comp"
  ],
  methods: {
    openResume: function ( ) {
      console.log ( this.$root )
      this.$root.openResume ( )
      // window.open('https://docs.google.com/document/d/1G8KbbnLW2bxeSr4dgKRv1XnjGX-P8OYZzHf8gV7bKGI/edit?usp=sharing', '_blank');
    }
  },
}
</script>

<style scoped>

@media (min-width: 600px) {
  .full-button {
    width: 80%;
    /* left: 10%; */
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
    margin: 15px;

  }
}
</style>