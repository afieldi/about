<template>
  <div class="background">
    <div class="background-tint" />
    <div class="welcome-block">
      <h1 class="display-3 welcome-title">Arek Fielding</h1>
      <hr style="background-color: white" />
      <p class="welcome-subtitle">My Website</p>
    </div>
    <div class="bottom-nav-bar" v-on:click="scroll()">
      <i class="fas fa-sort-down down-icon mx-auto"></i>
    </div>
  </div>
</template>

<script>
module.exports = {
  props: ["personName"],
  data: function() {
    return {
      test: "hello"
    }
  },
  methods: {
    scroll: function  ( ) {
        $('html,body').animate({
            scrollTop: $("#profile").offset().top},
            'slow');
    }
  }
};
</script>

<style scoped>

.welcome-title {
  color: white;
  font-family: Cambria, Cochin, Georgia, Times, 'Times New Roman', serif;
}

.welcome-subtitle {
  font-size: xx-large;
  color: white;
  font-family: Cambria, Cochin, Georgia, Times, 'Times New Roman', serif;
}

.welcome-block {
  left: 50%;
  top: 42%;
  position: absolute;
  transform: translateX(-50%) translateY(-50%);
  text-align: center;
}

.background {
  height: 100vh;
  background-image: url("../assets/images/296806.jpg");
  filter: blur(0px) grayscale(0.8);
}

.background-tint {
  height: 100%;
  width: 100%;
  position: absolute;
  opacity: 0.25;
  background-color: rgb(140, 5, 5);
}

.bottom-nav-bar {
  position: absolute;
  bottom: 0;
  height: 50px;
  width: 100%;
  background-color: #343a40;
  font-size: 2em;
}

.bottom-nav-bar:hover {
  cursor: pointer;
}

.bottom-nav-bar .down-icon {
  color: white;
  position: relative;
  left: 50%;
  transform: translateX(-50%);
}

</style>