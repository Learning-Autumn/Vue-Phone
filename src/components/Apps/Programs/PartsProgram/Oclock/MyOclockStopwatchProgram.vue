<template>
  <div class="oclock__stopwatch">
    <p class="oclock__stop">{{ fixationMinutes }}:{{ fixationSeconds }},{{ fixationMilliseconds }}</p>
    <div class="oclock__control">
      <button @click="addLap" @dblclick="clearLaps" class="oclock__control-btn oclock__control-btn--left" type="">
        Lap
      </button>
      <div class="oclock__control-sliders">
        <div class="oclock__control-slider oclock__control-slider--present"></div>
        <div class="oclock__control-slider oclock__control-slider--next"></div>
      </div>
      <button @click="controlStopwatch" class="oclock__control-btn oclock__control-btn--right" type="">
        Start
      </button>
    </div>
    <div class="oclock__stopwatch-laps">
      <ul class="oclock__laps-list">
        <li v-for="([key, value]) in Object.entries(lapsList)" class="oclock__lap-item" v-bind:key="key">
          <div class="oclock__lap-num">{{ Number(key) + 1}}</div>
          <div class="oclock__lap-time">{{value}}</div>
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      fixationMinutes: '00',
      fixationSeconds: '00',
      fixationMilliseconds: '00',
      isActiveStopwatch: false,
      stopwatch: null,
      lapsList: {},
    }
  },
  methods: {
    controlStopwatch(){
      if (this.isActiveStopwatch) {
        clearInterval(this.stopwatch)
        this.isActiveStopwatch = false
      } else {
        this.stopwatch = setInterval(() => {this.updateStopwatch()}, 10);
        this.isActiveStopwatch = true
      }
    },
    updateStopwatch(){
      let currentMilliseconds = Number(this.fixationMilliseconds) + 1
      let currentSeconds = Number(this.fixationSeconds) + 1
      let currentMinutes = Number(this.fixationMinutes) + 1

      if (currentSeconds === 60){
        this.fixationMinutes = String(currentMinutes).padStart(2, '0')
        this.fixationSeconds = '00'
      }
      else if (currentMilliseconds === 100) {
        this.fixationSeconds = String(currentSeconds).padStart(2, '0')
        this.fixationMilliseconds = '00'
      } else {
        this.fixationMilliseconds = String(currentMilliseconds).padStart(2, '0')
      }

    },
    addLap(){
      let objLength = Object.keys(this.lapsList).length
      let currentTime = `${this.fixationMinutes}:${this.fixationSeconds},${this.fixationMilliseconds}`
      if (this.lapsList[objLength - 1] !== currentTime && currentTime !== `00:00,00`){
        this.$set(this.lapsList, objLength, currentTime)
      }
    },
    clearLaps(){
      this.lapsList = {}
    }
  },
};
</script>

<style scoped>
.oclock__stopwatch {
  display: flex;
  justify-content: start;
  align-items: center;
  flex-direction: column;
  height: 100%;
  margin-top: 150px;
  /* padding-bottom: 120px; */
}
.oclock__stop {
  width: 300px;
  font-size: 76px;
  font-weight: 300;
  margin-bottom: 80px;
}
.oclock__control {
  display: flex;
  justify-content: space-between;
  align-items: center;
  width: 100%;
  padding: 0 15px;
}
.oclock__control-btn {
  width: 70px;
  height: 70px;
  border-radius: 50%;
  cursor: pointer;
}
.oclock__control-btn--left {
  background-color: #1c1c1e;
  border: none;
  color: #848484;
}
.oclock__control-btn--right {
  background-color: #092911;
  border: none;
  color: #5dcb85;
}

.oclock__control-sliders {
  display: flex;
  gap: 7px;
}

.oclock__stopwatch-laps {
  width: 100%;
  margin-top: 15px;
  padding: 0 15px;
  overflow-y: auto;
  height: 150px;
}


/* Стилізація полоси прокрутки для браузерів на основі WebKit */
.oclock__stopwatch-laps::-webkit-scrollbar {
  width: 8px;
}

.oclock__stopwatch-laps::-webkit-scrollbar-track {
  background: #262628;
  border-radius: 10px;
  
}

.oclock__stopwatch-laps::-webkit-scrollbar-thumb {
  background-color: #ff9f0a; 
  border-radius: 10px;
  border: 2px solid #262628; 
}

.oclock__stopwatch-laps::-webkit-scrollbar-thumb:hover {
  background-color: #ff7a00; 
}

.oclock__control-slider {
  width: 6px;
  height: 6px;
  border-radius: 50%;
}

.oclock__control-slider--present {
  background-color: white;
}
.oclock__control-slider--next {
  background-color: #848484;;
}
.oclock__laps-list {
  list-style: none;
}
.oclock__lap-item {
  display: flex;
  justify-content: space-between;
  border-bottom: 1px solid rgba(132, 132, 132, 0.3);
  border-top: 1px solid rgba(132, 132, 132, 0.3);
  font-size: 16px;
  padding: 10px 0px;
  font-style: italic;
}
.oclock__lap-num {

}
</style>
