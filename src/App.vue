<template>
  <div id="app">
    <div>
      <Chart class="small"/>
    </div>
    <!-- <div class="small">
      <Chart/>
    </div> -->
  </div>
</template>

<script>
import Chart from './components/Chart.vue'

export default {
  name: 'App',
  components: {
    Chart
  }
}
</script>

<style>
.small {
  border: 4px solid #C4C4C4;
  height: 200px;
}
</style>
