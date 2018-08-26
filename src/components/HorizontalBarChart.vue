<template>
<div class="Lchart">
    <canvas id="horizontalbar-chart"></canvas>
</div>
</template>

<script>
import Chart from "chart.js";
import { horizontalbarChartData } from "../chart-data.js";
export default {
  name: "HorizontalBarChart",
  data() {
    return {
      horizontalbarChartData: horizontalbarChartData
    };
  },

  mounted() {
    console.log("this = " + this);
    console.log(this.LineChartData);
    this.createChart("horizontalbar-chart", this.horizontalbarChartData);
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
