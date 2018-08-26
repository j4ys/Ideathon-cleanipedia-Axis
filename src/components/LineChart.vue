<template>
<div class="Lchart">
    <canvas id="planet-chart"></canvas>
</div>
</template>

<script>
import Chart from "chart.js";
import { LineChartData } from "../chart-data.js";
export default {
  name: "LineChart",
  data() {
    return {
      LineChartData: LineChartData
    };
  },

  mounted() {
    this.createChart("planet-chart", this.LineChartData);
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
