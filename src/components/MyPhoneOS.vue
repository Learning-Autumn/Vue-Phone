<template>
  <div class="os__inner" v-if="isOpen && isLoads">
    <MyLockScreen v-if="!isUnlocked && !isOpenProg" :toggleUnlock="toggleUnlock" />
    <MyWorkDesk v-else-if="!isOpenProg" />
  </div>
</template>

<script>
import MyLockScreen from './MyLockScreen.vue';
import MyWorkDesk from './MyWorkDesk.vue';

export default {
  components: {
    MyLockScreen, MyWorkDesk
  },
  data() {
    return {
      isUnlocked: false,
    }
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
    isOpenProg: {
      type: Boolean,
      required: true,
    },
  },
  methods: {
    toggleUnlock() {
      this.isUnlocked = !this.isUnlocked;
    },
    setUnlocked(value) {
      this.isUnlocked = value;
    }
  }
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