<template>
  <div class="home">
    <BarChart
      class="chart"
      :data-set="data"
      :margin-left="40"
      :margin-top="40"
      :tick-count="5"
      :bar-padding="0.5"
    />
  </div>
</template>

<script>
import BarChart from "./BarChart";

export default {
  name: "home",
  data() {
    return {
      data: [
        ["Bob", 23],
        ["Robin", 25],
        ["Mark", 29],
        ["Joe", 38],
        ["Eve", 34],
        ["Karen", 35],
        // ["Kirsty", 25],
        // ["Chris", 30],
      ],
    };
  },
  components: {
    BarChart,
  },
};
</script>

<style scoped>
.chart {
  margin: 40px auto 0;
  display: block;
}
</style>
