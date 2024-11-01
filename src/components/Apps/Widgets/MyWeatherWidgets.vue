<template>
  <div @click="openApp" class="work__desp-widget--weather">
    <p class="work__widget-local">Київ</p>
    <p class="work__widget-temper">11°</p>
    <p class="work__widget-status">Сонячно</p>
    <p class="work__widget-desp">B:15° H:4°</p>
  </div>
</template>

<script>
export default {
  inject: ['setProgram'],
  methods: {
    openApp() {
      this.setProgram('WeatherWidgets');
    }
  }
}
</script>

<style scoped>
.work__desp-widget--weather {
  background: rgb(41, 41, 200);
  background: linear-gradient(180deg, rgba(41, 41, 200, 1) 0%, rgba(0, 212, 255, 1) 100%);
}

.work__widget-local {
  font-weight: normal;
  margin-bottom: 5px;
}

.work__widget-temper {
  font-size: 35px;
  margin-bottom: 25px;
}

.work__widget-status {
  font-size: 12px;
}

.work__widget-desp {
  font-size: 12px;
}
</style>