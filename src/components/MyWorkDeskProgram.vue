<template>
  <div>
    <MyCameraProgram v-if="state.isOpenProgram === 'CameraApp'" />
    <MyMapProgram v-if="state.isOpenProgram === 'MapApp'" />
    <MyCalculatorProgram v-if="state.isOpenProgram === 'CalculatorApp'" />
  </div>
</template>

<script>
import MyCalculatorProgram from "./Apps/Programs/MyCalculatorProgram.vue";
import MyCameraProgram from "./Apps/Programs/MyCameraProgram.vue";
import MyMapProgram from "./Apps/Programs/MyMapProgram.vue";
export default {
  inject: ["state"],
  components: { MyCameraProgram, MyMapProgram, MyCalculatorProgram },
};
</script>

<style scoped></style>
