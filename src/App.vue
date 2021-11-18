<template>
  <div>
    <Lighting msg="Caribbean Courtyard Villa" />
    <Weather />
  </div>
</template>

<script>
import LightingVue from "./components/Lighting.vue";
import WeatherVue from "./components/Weather.vue";

export default {
  name: "App",
  components: {
    Lighting: LightingVue,
    Weather: WeatherVue,
  },
};
</script>

<style>
@import url("https://fonts.googleapis.com/css?family=Rubik");
</style>
