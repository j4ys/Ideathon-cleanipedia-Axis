<template>
  <div id="container">
    <Head></Head>
    <DataViz></DataViz>
  </div>
</template>

<script>
import Head from "./components/Head";
import InputBlock from "./components/InputBlock";
import DataViz from "./components/DataViz";

export default {
  name: "App",
  components: {
    Head,
    InputBlock,
    DataViz
  }
};
</script>

<style>
* {
  margin: 0;
  padding: 0;
}
#container {
  display: grid;
  grid-template-rows: 50px 100px 1fr 1fr;
  grid-row-gap: 5px;
}
</style>
