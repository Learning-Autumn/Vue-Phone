<template>
  <div class="oclock__programs">
    <div v-if="currentMenu === 'WorldClock'" class="oclock__program">
      <MyOclockOclockProgram/>
    </div>
    <div v-else-if="currentMenu === 'Alarms'" class="oclock__program">
      <!-- <MyOclockControl class="oclock__program-control" /> -->
      <MyOclockAlarmsProgram/>
    </div>
    <div v-else-if="currentMenu === 'Stopwatch'" class="oclock__program">
      <MyOclockStopwatchProgram/>
    </div>
    <div v-else-if="currentMenu === 'Timers'" class="oclock__program">
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
      currentMenu: "WorldClock"
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
.oclock__programs {
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

.oclock__program {
  height: 550px;
  /* overflow: hidden; */
}

</style>