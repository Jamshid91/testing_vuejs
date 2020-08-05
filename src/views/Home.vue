<template>
  <div class="home">
    <h1>Hello</h1>
    <BarChart class="chart" />
  </div>
</template>

<script>
import BarChart from "@/components/BarChart.vue";

export default {
  name: "home",
  components: { BarChart },
};
</script>

<style lang="scss" scoped>
.chart {
  margin: 120px auto;
  display: block;
}
</style>