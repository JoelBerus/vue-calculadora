<template>
  <img alt="Vue logo" src="./assets/logo.png" />
  <Formulario msg="Formulario de consumo" />
</template>

<script>
import Formulario from "./components/Formulario.vue";
export default {
  name: "App",
  components: {
    Formulario,
  },
  data() {
    return {
      value: 0,
    };
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
