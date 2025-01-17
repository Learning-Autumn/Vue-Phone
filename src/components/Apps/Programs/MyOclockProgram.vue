<template>
  <div class="oclock__program">
    <div v-if="currentMenu === 'WorldClock'" class="world__oclock">
      <MyOclockOclockProgram/>
    </div>
    <div v-else-if="currentMenu === 'Alarms'" class="world__oclock">
      <!-- <MyOclockControl class="oclock__program-control" /> -->
      <MyOclockAlarmsProgram/>
    </div>
    <div v-else-if="currentMenu === 'Stopwatch'" class="world__oclock">
      <MyOclockStopwatchProgram/>
    </div>
    <div v-else-if="currentMenu === 'Timers'" class="world__oclock">
      <MyOclockTimersProgram/>
    </div>
    <MyOclockMenu class="oclock__program-menu" :isOpenMenu="currentMenu" @updateMenu="updateCurrentMenu"/>
  </div>
</template>

<script>
import MyOclockMenu from './PartsProgram/Oclock/MyOclockMenu.vue';
import MyOclockAlarmsProgram from './PartsProgram/Oclock/Alarms/MyOclockAlarmsProgram.vue';
import MyOclockOclockProgram from './PartsProgram/Oclock/WorldOclock/MyOclockWorldProgram.vue';
import MyOclockStopwatchProgram from './PartsProgram/Oclock/Stopwatch/MyOclockStopwatchProgram.vue';
import MyOclockTimersProgram from './PartsProgram/Oclock/Timers/MyOclockTimersProgram.vue';

export default {
  components: { MyOclockMenu, MyOclockAlarmsProgram, MyOclockOclockProgram, MyOclockStopwatchProgram, MyOclockTimersProgram },
  data() {
    return {
      currentMenu: "Alarms"
    }
  },
  methods: {
    updateCurrentMenu(newMenu) {
      this.currentMenu = newMenu; 
    }
  }
}
</script>

<style scoped>
.oclock__program {
  width: 335px;
  height: 705px;
  padding: 50px 10px 15px;
}


.oclock__program-menu {
  position: absolute;
  left: 0;
  right: 0;
  bottom: 20px;
}

.world__oclock {
  height: 550px;
  /* overflow: hidden; */
}

</style>