<template>
  <div class="oclock__timers">

    <div class="oclock__program-inner">
      <p class="oclock__control-text">
        Edit
      </p>
    </div>

    <h2 class="oclock__program-title">Timers</h2>

    <div class="oclock__timers-edit" v-if="isShowMode">
      <MyOclockTimersSlider ref="timerData"></MyOclockTimersSlider>
    </div>

    <div class="oclock__timers-show" v-else>
      Time
    </div>

    <div class="oclock__timers-control">
      <button class="oclock__control-btn oclock__control-btn--left" type="">
        Cancel
      </button>
      <button 
        @click="startTimers"
        class="oclock__control-btn oclock__control-btn--right" 
        type=""
      >
        Start
      </button>
    </div>

    <div class="oclock__desc">
      <ul class="oclock__desc-list">
        <li class="oclock__desc-item">
          <p class="oclock__desc-item-title">Label</p>
          <p class="oclock__desc-item-title oclock__desc-item-title--timer">Timer</p>
        </li>
        <hr class="oclock__desc-line" />
        <li class="oclock__desc-item">
          <p class="oclock__desc-item-title">When Timer Ends</p>
          <p class="oclock__desc-item-title oclock__desc-item-title--radial">Radial</p>
        </li>
      </ul>
    </div>

    <h6 class="oclock__program-list-desc">Recents</h6>
    <ul class="oclock__program-list">
      <MyOclockTimersItem v-for="(item, index) in dataTimers" :Time="item.Time" :TimeLeft="item.TimeLeft" :isActive="item.isActive" :key="index"/>
    </ul>
  </div>
</template>

<script>
import MyOclockTimersSlider from "./MyOclockTimersSlider.vue";
import MyOclockTimersItem from "./MyOclockTimersItem.vue";


export default {
  components: { MyOclockTimersSlider, MyOclockTimersItem },
  data() {
    return {
      isShowMode: true,
      isShowTime: "",
      dataTimers: [
        {
          'Time': {
            'minutes': 20,
            'seconds': 13
          },
          'TimeLeft': {
            'minutes': 20,
            'seconds': 13
          },
          'isActive': true,
        },
        {
          'Time': {
            'minutes': 20,
            'seconds': 13
          },
          'TimeLeft': {
            'minutes': 20,
            'seconds': 13
          },
          'isActive': true,
        }
      ]
    }
  },
  methods: {
    startTimers(){
      this.isShowMode = !this.isShowMode;
      const timer = this.$refs.timerData.addTimerData()
      console.log(timer);
      
      this.dataTimers.push(timer)
    }
  }
};
</script>

<style scoped>
.oclock__program-inner {
  display: flex;
  justify-content: space-between;
  color: #ff9f0a;
  font-size: 16px;
  display: flex;
  align-items: center;
  font-weight: 300;
  margin-bottom: 10px;
  height: 28px;
}

.oclock__program-title {
  font-size: 26px;
  margin-bottom: 20px;
}

.oclock__timers-show {
  height: 190px;
}

.oclock__control-btn {
  width: 70px;
  height: 70px;
  border-radius: 50%;
  cursor: pointer;
  margin-bottom: 25px;
}

.oclock__timers-control {
  display: flex;
  justify-content: space-between;
  align-items: center;
  width: 100%;
  padding: 0 15px;
}

.oclock__control-btn--left {
  background-color: #1c1c1e;
  border: none;
  color: #848484;
}
.oclock__control-btn--right {
  background-color: #010b03;
  border: none;
  color: #5dcb85;
}

.oclock__desc {
  display: flex;
  flex-direction: column;
  background-color: #1c1c1e;
  border-radius: 15px;
  padding: 15px;
  font-size: 13px;
  margin-bottom: 20px;
}

.oclock__desc-list {
  font-size: 14.5px;
}

.oclock__desc-item {
  display: flex;
  justify-content: space-between;
}

.oclock__desc-line {
  border-top-color: #28282a;
}

.oclock__desc-item-title--timer {
  color: #848484;
}

.oclock__desc-item-title--radial {
  color: #adadaf;
}

.oclock__program-list {
  overflow-y: auto;
  height: 65px;
}

/* Стилізація полоси прокрутки для браузерів на основі WebKit */
.oclock__program-list::-webkit-scrollbar {
  width: 8px;
}

.oclock__program-list::-webkit-scrollbar-track {
  background: #262628;
  border-radius: 10px;
  
}

.oclock__program-list::-webkit-scrollbar-thumb {
  background-color: #ff9f0a; 
  border-radius: 10px;
  border: 2px solid #262628; 
}

.oclock__program-list::-webkit-scrollbar-thumb:hover {
  background-color: #ff7a00; 
}

.oclock__program-list-desc {
  font-size: 18px;
  margin-bottom: 5px;
  padding-bottom: 5px;
  border-bottom: 1px solid rgba(132, 132, 132, 0.3);
}
</style>
