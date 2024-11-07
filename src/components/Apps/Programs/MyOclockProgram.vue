<template>
  <div class="oclock__program">
    <div v-if="currentMenu === 'WorldClock'" class="world__oclock">
      <MyOclockControl class="oclock__program-control" />
      <h2 class="oclock__program-title">
        World Clock
      </h2>
      <ul class="world__oclock-list">
        <li class="world__oclock-item">
          <div class="world__oclock-item-left">
            <p class="world__oclock-top">Today, +0HRS</p>
            <p class="world__oclock-bottom">Kyiv</p>
          </div>
          <div class="world__oclock-item-right">
            <p class="world__oclock-time">23:30</p>
          </div>
        </li>
      </ul>
    </div>
    <div v-else-if="currentMenu === 'Alarms'" class="world__oclock">
      <MyOclockControl class="oclock__program-control" />
      <h2 class="oclock__program-title">
        Alarms
      </h2>
      <ul class="world__oclock-list">
        <li class="world__oclock-item">
          <div class="world__oclock-item-left">
            <p class="world__oclock-top">Today, +0HRS</p>
            <p class="world__oclock-bottom">Kyiv</p>
          </div>
          <div class="world__oclock-item-right">
            <p class="world__oclock-time">23:30</p>
          </div>
        </li>
      </ul>
    </div>
    <MyOclockMenu class="oclock__program-menu" :isOpenMenu="currentMenu" @updateMenu="updateCurrentMenu"/>
  </div>
</template>

<script>
import MyOclockControl from './PartsProgram/Oclock/MyOclockControl.vue';
import MyOclockMenu from './PartsProgram/Oclock/MyOclockMenu.vue';
export default {
  components: { MyOclockControl, MyOclockMenu },
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
.oclock__program {
  width: 335px;
  height: 705px;
  padding: 50px 10px 15px;
}

.oclock__program-control {
  margin-bottom: 10px;
}

.oclock__program-title {
  font-size: 26px;
  margin-bottom: 20px;
}

.world__oclock-list {
  list-style: none;
}

.world__oclock-item {
  display: flex;
  padding: 20px 0;
  align-items: center;
  justify-content: space-between;
  border-top: 1px solid rgba(132, 132, 132, 0.3);
  border-bottom: 1px solid rgba(132, 132, 132, 0.3);
}

.world__oclock-top {
  font-size: 14px;
  color: #848484;
  margin-bottom: 5px;
}

.world__oclock-bottom {
  font-size: 26px;
  font-weight: 300;
}

.world__oclock-time {
  font-size: 50px;
  font-weight: 300;
}

.oclock__program-menu {
  position: absolute;
  left: 0;
  right: 0;
  bottom: 20px;
}
</style>