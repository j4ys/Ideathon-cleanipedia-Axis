<template>
 
  <div class="chart-container">
  <LineChart></LineChart>
  <PieChart></PieChart>
  <BarChart></BarChart>
  <horizontalbarChart></horizontalbarChart>
  </div>
</template>


<script>
import LineChart from "./LineChart";
import PieChart from "./PieChart";
import BarChart from "./BarChart";
import horizontalbarChart from "./HorizontalBarChart";

export default {
  name: "DataViz",
  components: {
    LineChart,
    PieChart,
    BarChart,
    horizontalbarChart
  }
};
</script>

<style scoped>
.chart-container {
  display: grid;
  grid-template-rows: repeat(2, 48%);
  grid-template-columns: repeat(2, 500px);
  grid-row: 3 / 5;
  grid-gap: 10px;
  margin: 10px auto;
}

.chart {
  background-color: pink;
  padding: 30px;
}
</style>
