<template>
  <div class="background">
    <div class="welcome-block">
      <h1 class="display-3 welcome-title">Arek Fielding</h1>
      <!-- <hr style="background-color: white" /> -->
      <!-- <p class="welcome-subtitle">My Website</p> -->
    </div>
  </div>
</template>

<script>
module.exports = {
  props: ["personName"]
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
  top: 37%;
  position: absolute;
  transform: translateX(-50%) translateY(-50%);
  text-align: center;
}

.background {
  height: 100vh;
  width: 100vw;
  background-image: url("../assets/296806.jpg");
  filter: blur(0px) grayscale(0.8);
}
</style>