<template>
<div class="holder">
  <div class="exp" v-bind:style="expStyle"></div>
  <div style="position: absolute; height: 100%; width: 100%; top: 0;">
    <div v-for="index in 10" :key="index" class="exp-cover" :style="{left: (index-1)*10 + '%'}"></div>
  </div>
</div>    
</template>

<script>
module.exports = {
  props: [
    "value"
  ],
  data: function ( ) {
    return {
      expStyle: {
        width: `${this.value}%`
      }
    }
  }
}
</script>

<style scoped>
.holder {
  width: 100%;
  height: 15px;
  background-color: #19241e;
  position: relative;
  margin-bottom: 5px;
  border-radius: 20px;
  overflow: hidden;
}

.exp {
  height: 100%;
  background-color: #a3de73;
  /* background-color: rgb(61, 218, 95); */
}

.exp-cover {
  width: 10%;
  display: inline-block;
  position: absolute;
  border: 2px black solid;
  height: 100%;
  top: 0;
  background: radial-gradient(circle, rgba(213, 213, 213, 0) 0%, rgba(0, 0, 0, 0.637) 100%);
}
</style>