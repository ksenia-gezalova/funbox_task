<template>
  <div id="app">
    <Main></Main>
  </div>
</template>

<script>
import Main from "./components/Main.vue";

export default {
  name: "app",
  components: {
    Main
  }
};
</script>

<style>
@font-face {
  font-family: "Exo 2 Thin", sans-serif;
  src: url("../src/assets/Exo2.0-Thin.otf") format("opentype");
  font-weight: lighter;
}

body {
  margin: 0;
  padding: 0;
  background-size: cover;
  font-family: "Exo 2 Thin", sans-serif;
}
</style>
