<template>
  <svg class="barchart" :width="width + marginLeft / 2" :height="height + marginTop">
    <g class="bars" fill="none">
      <rect
        v-for="(bar, index) in bars"
        fill="pink"
        :key="index"
        :height="bar.height"
        :width="bar.width"
        :x="bar.x"
        :y="bar.y"
      />
    </g>
  </svg>
</template>

<script>
import { scaleLinear, scaleBand } from "d3-scale";

export default {
  name: "BarChart2",
  props: {
     height: { default: 100 },
    width: { default: 150 },
    dataSet: { default: [] },
    marginLeft: { default: 0 },
    marginTop: { default: 0 },
    marginBottom: { default: 0 },
    marginRight: { default: 0 },
    tickCount: { default: 0 },
    barPadding: { default: 0.3 },
  },

  computed: {
    yTicks() {
      return this.y.ticks(this.tickCount);
    },
    x() {
      return scaleBand()
        .range([0, this.width])
        .padding(this.barPadding)
        .domain(this.dataSet.map((e) => e[0]));
    },
    y() {
      let values = this.dataSet.map((e) => e[1]);
      return scaleLinear()
        .range([this.height, 0])
        .domain([0, Math.max(...values)]);
    },
    bars() {
      let bars = this.dataSet.map((d) => {
        return {
          xLabel: d[0],
          x: this.x(d[0]),
          y: this.y(d[1]),
          width: this.x.bandwidth(),
          height: this.height - this.y(d[1]),
        };
      });

      return bars;
    },
  },
};
</script>

<style scoped>
.chart[data-v-7ba5bd90] {
  margin: 0;
}
</style>
