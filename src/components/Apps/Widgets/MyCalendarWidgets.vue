<template>
  <div class="work__desp-widget--calendar">
    <p class="work__widget-days">{{ currentTimeData.dayName }}</p>
    <p class="work__widget-day">{{ currentTimeData.dayNumber }}</p>
  </div>
</template>

<script>
export default {
  inject: ["currentTimeData"],
};
</script>

<style scoped>
.work__widget-days {
  text-transform: uppercase;
  color: #e25e67;
  font-size: 12px;
  margin-bottom: 5px;
}

.work__widget-day {
  font-size: 25px;
}

.work__desp-widget--calendar {
  background: rgb(0, 0, 0);
  background: linear-gradient(190deg, rgba(0, 0, 0, 1) 0%, rgba(51, 2, 2, 1) 100%);
}
</style>
