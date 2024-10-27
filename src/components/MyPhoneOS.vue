<template>
  <div class="os__inner" v-if="isOpen && isLoads">
    <MyLockScreen/>
  </div>
</template>

<script>
import MyLockScreen from './MyLockScreen.vue';

export default {
  components: {
    MyLockScreen
  },
  props: {
    isOpen: {
      type: Boolean,
      required: true,
    },
    isLoads: {
      type: Boolean,
      required: true,
    },
  },
};
</script>

<style scoped>
.os__inner {
  position: absolute;
  height: 695px;
  display: flex;
  justify-content: center;
  align-items: center;
  top: 80px;
  width: 320px;
}
</style>