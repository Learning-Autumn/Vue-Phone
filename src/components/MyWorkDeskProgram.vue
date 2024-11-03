<template>
  <div>
    <MyCameraProgram v-if="state.isOpenProgram === 'CameraApp'" />
    <MyMapProgram v-if="state.isOpenProgram === 'MapApp'" />
    <MyCalculatorProgram v-if="state.isOpenProgram === 'CalculatorApp'" />
    <MyWeatherProgram v-if="state.isOpenProgram === 'WeatherWidgets'" />
  </div>
</template>

<script>
import MyCalculatorProgram from "./Apps/Programs/MyCalculatorProgram.vue";
import MyCameraProgram from "./Apps/Programs/MyCameraProgram.vue";
import MyMapProgram from "./Apps/Programs/MyMapProgram.vue";
import MyWeatherProgram from "./Apps/Programs/MyWeatherProgram.vue";
export default {
  inject: ["state"],
  components: { MyCameraProgram, MyMapProgram, MyCalculatorProgram, MyWeatherProgram },
};
</script>

<style scoped></style>
