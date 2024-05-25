<template>
  <Dashboard />
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'

import Dashboard from "./components/Dashboard.vue";
import "@mdi/font/css/materialdesignicons.min.css";
export default {
  name: "App",
  components: {
    // HelloWorld,
    Dashboard,
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  /* text-align: center; */
  color: #2c3e50;
  /* margin-top: 60px; */
  max-width: 1560px;
  margin: auto;
}
body {
  margin: 0px;
}
</style>
