<template>
<div class="Lchart">
    <canvas id="bar-chart"></canvas>
</div>
</template>

<script>
import Chart from "chart.js";
import { BarChartData } from "../chart-data.js";
export default {
  name: "BarChart",
  data() {
    return {
      BarChartData: BarChartData
    };
  },

  mounted() {
    console.log("this = " + this);
    console.log(this.LineChartData);
    this.createChart("bar-chart", this.BarChartData);
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
