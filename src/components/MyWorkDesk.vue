<template>
  <div class="work__desk">
    <div class="work__desk-inner">
      <div class="work__desk-top">
        <div class="work__desk-time">
          {{ currentTimeData.currentTime }}
        </div>
        <img class="work__desk-photo" src="/images/phone.png" alt="" />
        <MyStatusPhone />
      </div>
      <MyWorkDeskApps v-if="!isOpenProgram" />
      <MyWorkDeskProgram v-else />
    </div>
  </div>
</template>

<script>
import MyStatusPhone from "./MyStatusPhone.vue";
import MyWorkDeskApps from "./MyWorkDeskApps.vue";
import MyWorkDeskProgram from "./MyWorkDeskProgram.vue";

export default {
  components: { MyStatusPhone, MyWorkDeskApps, MyWorkDeskProgram },
  inject: ["state", "currentTimeData"],
  computed: {
    isOpenProgram() {
      return this.state.isOpenProgram;
    },
  },
};
</script>

<style scoped>
.work__desk-top {
  display: flex;
  justify-content: space-between;
  position: absolute;
  right: 0;
  left: 0;
  top: 0;
  padding: 12px 20px;
  align-items: center;
  z-index: 1000;
}
.work__desk-photo {
  position: absolute;
  left: 0;
  right: 0;
  margin: 0 auto;
  z-index: 10;
}
</style>
