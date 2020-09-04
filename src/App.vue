<template>
  <div id="app">
    <Cinemagraphs/>
  </div>
</template>

<script>
import Cinemagraphs from "./components/Cinemagraphs.vue";

export default {
  name: "App",
  components: {
    Cinemagraphs,
  }
};
</script>

<style>
body{
  padding: 0px;
  margin: 0px;
  position: fixed;
  overflow: hidden;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin: 0px;
  padding: 0px;
}
</style>
