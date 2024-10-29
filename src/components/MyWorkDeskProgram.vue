<template>
  <div>
    <MyCameraProgram v-if="state.isOpenProgram === 'CameraApp'"/>
    <MyMapProgram v-if="state.isOpenProgram === 'MapApp'"/>
  </div>
</template>

<script>
import MyCameraProgram from './Apps/Programs/MyCameraProgram.vue';
import MyMapProgram from './Apps/Programs/MyMapProgram.vue';
  export default {
    inject: ['state'],
    components: { MyCameraProgram, MyMapProgram }
  }
</script>

<style scoped>

</style>