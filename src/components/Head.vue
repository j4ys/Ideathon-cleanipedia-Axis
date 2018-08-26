<template>
  <nav>
  <span class="heading">Dashboard</span>
  </nav>
  
</template>
<script>
export default {
  name: "Head"
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
nav {
  width: 100%;
  background-color: #009688;
  display: flex;
  padding: 0px;
  justify-content: space-around;
  grid-row: 1 / 2;
}
.heading {
  text-transform: uppercase;
  color: white;
  font-size: 25px;
  font-weight: 700;
  align-self: center;
  font-family: Cuprum;
}
</style>
