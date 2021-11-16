<template>
  <HelloWorld msg="Caribbean Courtyard Villa" />
  <Weather />
</template>

<script>
import LightingVue from "./components/Lighting.vue";
import WeatherVue from "./components/Weather.vue";

export default {
  name: "App",
  components: {
    HelloWorld: LightingVue,
    Weather: WeatherVue,
  },
};
</script>

<style>
@import url("https://fonts.googleapis.com/css?family=Rubik");

#app {
  font-family: "Rubik", sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #ddd;
  margin-top: 160px;
}
</style>
