<template>
  <div>
    <MyCameraProgram v-if="state.isOpenProgram === 'CameraApp'" />
    <MyMapProgram v-if="state.isOpenProgram === 'MapApp'" />
    <MyCalculatorProgram v-if="state.isOpenProgram === 'CalculatorApp'" />
    <MyWeatherProgram v-if="state.isOpenProgram === 'WeatherWidgets'" />
    <MyPinPongProgram v-if="state.isOpenProgram === 'PinPongApp'" />
    <MyOclockProgram v-if="state.isOpenProgram === 'OclockApp'" />
    <MyPhoneProgram v-if="state.isOpenProgram === 'Phone'"></MyPhoneProgram>
  </div>
</template>

<script>
import MyCalculatorProgram from "./Apps/Programs/MyCalculatorProgram.vue";
import MyCameraProgram from "./Apps/Programs/MyCameraProgram.vue";
import MyMapProgram from "./Apps/Programs/MyMapProgram.vue";
import MyPinPongProgram from "./Apps/Programs/MyPinPongProgram.vue";
import MyWeatherProgram from "./Apps/Programs/MyWeatherProgram.vue";
import MyOclockProgram from "./Apps/Programs/MyOclockProgram.vue";
import MyPhoneProgram from "./Apps/Programs/MyPhoneProgram.vue";


export default {
  inject: ["state"],
  components: { MyCameraProgram, MyMapProgram, MyCalculatorProgram, MyWeatherProgram, MyPinPongProgram, MyOclockProgram, MyPhoneProgram },
};
</script>

<style scoped></style>
