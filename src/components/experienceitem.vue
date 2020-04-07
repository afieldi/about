<template>
  <div class="row">
    <div v-if="!flip" class="col-sm-3">
      <h5>{{expObj.displayName}}</h5>
      <a><b>{{expObj.role}}</b></a>
      <p><i>{{expObj.startDate}} - {{expObj.endDate}}</i></p>
    </div>
    <div class="col-sm-8">
      <ul>
        <li v-for="bp in expObj.bullets" :key="bp">{{bp}}</li>
      </ul>
      <!-- <hr style="background-color: grey;"> -->

    </div>
    <div v-if="flip" class="col-sm-3">
      <h5>{{expObj.displayName}}</h5>
      <a><b>{{expObj.role}}</b></a>
      <p><i>{{expObj.startDate}} - {{expObj.endDate}}</i></p>
    </div>
  </div>
  
</template>

<script>
export default {
  props: [
    "expObj",
    "flip"
  ]
}
</script>