<template>
  <div class="oclock__alarms">
    <MyOclockControl :parentId="'AlarmsOclock'" @add-click="handleAdd" />
    <h2 class="oclock__program-title">
      Alarms
    </h2>
    <div v-if="!isDateLineAlarms && !isInput" class="oclock__alerms-content">
      <p class="oclock__program-desc">
        <svg fill="#fff" width="18px" height="18px" viewBox="0 0 50 50" xmlns="http://www.w3.org/2000/svg"
          xmlns:xlink="http://www.w3.org/1999/xlink" stroke="#fff">
          <g id="SVGRepo_bgCarrier" stroke-width="0"></g>
          <g id="SVGRepo_tracerCarrier" stroke-linecap="round" stroke-linejoin="round"></g>
          <g id="SVGRepo_iconCarrier">
            <path
              d="M5 10C3.347656 10 2 11.347656 2 13L2 26.8125C3.296875 25.6875 4.9375 24.777344 7 24.0625L7 20C7 17.339844 11.542969 17 15.5 17C19.457031 17 24 17.339844 24 20L24 22C24.335938 21.996094 24.65625 22 25 22C25.34375 22 25.664063 21.996094 26 22L26 20C26 17.339844 30.542969 17 34.5 17C38.457031 17 43 17.339844 43 20L43 24.03125C45.058594 24.742188 46.691406 25.671875 48 26.8125L48 13C48 11.347656 46.652344 10 45 10 Z M 25 24C5.90625 24 -0.015625 27.53125 0 37L50 37C50.015625 27.46875 44.09375 24 25 24 Z M 0 39L0 50L7 50L7 46C7 44.5625 7.5625 44 9 44L41 44C42.4375 44 43 44.5625 43 46L43 50L50 50L50 39Z">
            </path>
          </g>
        </svg>
        Sleep | Wake Up
      </p>
      <div class="oclock__program-set">
        <p class="oclock__program-set--text">
          No Alarm
        </p>
        <p class="oclock__program-set-action">
          set up
        </p>
      </div>
      <ul class="oclock__program-list">
        <MyOclockAlarmsItem v-for="(item, index) in this.dataAlarms" :key="index" :Time="item.Time" :isActive="item.isActive" />
      </ul>
    </div>
    
    <div v-else-if="!isDateLineAlarms && isInput" class="clock__program-add">
      <!-- <p class="clock__program-info">{{ this.infoWorld }}</p> -->
      <MyOclockAlarmsSlider @addTime="fetchTime"/>
      <!-- <input class="clock__program-input" placeholder="Введіть місто" v-model="isTime" type="" name="" value="">
      <button class="clock__program-btn" @click="fetchTime" type="">Add</button> -->
    </div>
    <div v-else :class="['oclock__alarms-time', {'oclock__alarms-time--dateLine': isDateLineAlarms}]">
      {{ isTimeDateLine }}
      <button 
        @click="cancelDateLineAlarms" 
        class="oclock__alarms-cancel"
      >
        Wake up!
      </button>
    </div>
  </div>
</template>

<script>
import MyOclockAlarmsItem from './MyOclockAlarmsItem.vue';
import MyOclockControl from '../MyOclockControl.vue';
import MyOclockAlarmsSlider from './MyOclockAlarmsSlider.vue';

export default {
  components: { MyOclockAlarmsItem, MyOclockControl, MyOclockAlarmsSlider },
  data() {
    return {
      isInput: false,
      isDateLineAlarms: false,
      isTimeDateLine: null,
      interval: null,
      audio: null,
      dataAlarms: [
        {
          'Time': '22:44', 
          'isActive': true,
        },
        {
          'Time': '02:30', 
          'isActive': false,
        },
        {
          'Time': '02:30', 
          'isActive': true,
        },
        {
          'Time': '02:30', 
          'isActive': false,
        },
        {
          'Time': '02:30', 
          'isActive': false,
        }
      ],
    }
  },
  methods: {
    handleAdd() {
      this.isInput = !this.isInput;
    },
    fetchTime(time) {
      this.dataAlarms.push(
        {
          'Time': time,
          'isActive': true,
        }
      )
      this.handleAdd()
    },
    cancelDateLineAlarms(){
      this.isDateLineAlarms = false
      this.startIntervalAlarms()
    },
    checkAlarms(){
      const now = new Date()
      const currentTime = now.toTimeString().slice(0, 5)
      this.dataAlarms.forEach(item => {
        if (item.isActive && item.Time === currentTime){
          clearInterval(this.interval)
          this.isTimeDateLine = currentTime
          this.startAlarmSignal()
        }
      });     
      
    },
    startAlarmSignal(){
      this.audio = new Audio(require('@/assets/audio/WhereIsMyMind.mp3'));
      this.isDateLineAlarms = true;
      this.audio.play().catch((error) => {
        console.error('Помилка відтворення:', error);
      })
    },
    startIntervalAlarms(){
      this.interval = setInterval(this.checkAlarms, 5000)
    },
  },
  mounted() {
    this.checkAlarms()
    this.startIntervalAlarms()
  },
}
</script>

<style scoped>
.oclock__program-title {
  font-size: 26px;
  margin-bottom: 20px;
}

.oclock__program-list {
  list-style: none;
  height: 400px;
  overflow-y: auto;
  padding-right: 10px;
  padding-bottom: 50px;
}

.oclock__alarms-time {
  display: flex;
  flex-direction: column;
  margin-top: 85px;
  font-size: 76px;
  justify-content: center;
  align-items: center;
  gap: 30px;
  text-align: center;
}

.oclock__alarms-time--dateLine {
  animation: text-grow-shrink 2s infinite;
}

@keyframes text-grow-shrink {
  0%, 100% {
    transform: scale(1); /* початковий розмір */
    color: #c7c7c7;
  }
  50% {
    transform: scale(1.05); /* збільшення на 25% */
    color: white;
  }
}

.oclock__alarms-cancel {
  background-color: #010b03;
  color: #5dcb85;
  border-radius: 50%;
  cursor: pointer;
  border: none;
  height: 70px;
  width: 70px;
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


.oclock__program-desc {
  display: flex;
  align-items: center;
  gap: 5px;
  margin-bottom: 10px;
}

.oclock__program-set {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 15px 0;
  border-top: 1px solid rgba(132, 132, 132, 0.3);
  border-bottom: 1px solid rgba(132, 132, 132, 0.3);
  color: #848484;
}

.oclock__program-set-action {
  text-transform: uppercase;
  color: #ff9f0a;
  font-size: 14px;
  margin-left: 10px;
  background-color: #262628;
  padding: 8px;
  border-radius: 10px;
}

</style>