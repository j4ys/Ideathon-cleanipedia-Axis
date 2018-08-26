<template>
<div class="Lchart">
    <canvas id="pie-chart"></canvas>
</div>
</template>

<script>
import Chart from "chart.js";
import { PieChartData } from "../chart-data.js";
export default {
  name: "LineChart",
  data() {
    return {
      planetChartData: PieChartData
    };
  },

  mounted() {
    console.log(this);
    console.log(this.planetChartData);
    this.createChart("pie-chart", this.planetChartData);
  },

  methods: {
    createChart(chartId, chartData) {
      const ctx = document.getElementById(chartId);
      const myChart = new Chart(ctx, {
        type: chartData.type,
        data: chartData.data,
        options: chartData.options
      });
    }
  }
};
</script>

<style>
#planet-chart {
  width: 500px;
}
</style>
