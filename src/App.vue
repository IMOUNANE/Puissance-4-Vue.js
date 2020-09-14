<template>
  <div id="app">
   
    <Tille />
    <Calculator/>
  </div>
</template>

<script>
import Title from "./components/Title.vue";
import Calculator from "./components/Calculator.vue";

export default {
  name: "App",
  components: {
    Title,
    Calculator
  }
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 30px;
}
</style>
