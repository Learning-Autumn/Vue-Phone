<template>
  <div class="world__program">
    <MyOclockControl :parentId="'WorldOclock'" @add-click="handleAdd" />
    <h2 class="oclock__program-title">
      World Clock
    </h2>
    <ul v-if="!isInput" class="clock__program-list">
      <li v-for="(item, index) in this.dataWorld" :key="index" class="oclock__program-item">
        <div class="woclock__program-item-left">
          <p class="oclock__program-top">Today, {{ item.Offset }}</p>
          <p class="oclock__program-bottom">{{ item.City }}</p>
        </div>
        <div class="oclock__program-item-right">
          <p class="oclock__program-time">{{ item.Time }}</p>
        </div>
      </li>
    </ul>
    <div v-else class="clock__program-add">
      <p class="clock__program-info">{{ this.infoWorld }}</p>
      <input class="clock__program-input" placeholder="Введіть місто" v-model="city" type="" name="" value="">
      <button class="clock__program-btn" @click="fetchTime" type="">Add</button>
    </div>
  </div>
</template>

<script>
import MyOclockControl from '../Oclock/MyOclockControl.vue';

export default {
  components: { MyOclockControl },
  data() {
    return {
      isInput: false,
      city: "London",
      dataWorld: [
        {
          City: "Kyiv",
          Offset: "+2HRS",
          Time: "08:40",
        }
      ],
      infoWorld: '',
    }
  },
  methods: {
    handleAdd() {
      this.isInput = !this.isInput;
    },
    fetchTime() {
      const apiKey = "TMMTPU1QA5BR";

      fetch(`http://api.timezonedb.com/v2.1/get-time-zone?key=${apiKey}&format=json&by=zone&zone=Europe/${this.city}`)
        .then(response => response.json())
        .then(data => {
          let formattedTime = data.formatted;

          let time = formattedTime.match(/(\d{2}):(\d{2})/);
          let cityName = data.zoneName.split('/')[1];
          const gmtOffset = data.gmtOffset;

          const offsetHours = gmtOffset / 3600;
          const offsetString = `+${offsetHours}HRS`; 

          
          if (time) {
            const cityExists = this.dataWorld.some(item => item.City === cityName);

            if (!cityExists) {
              this.dataWorld.push({
                'City': cityName,
                'Time': `${time[1]}:${time[2]}`,
                'Offset': offsetString,
              });
              this.city = '';
              this.isInput = false;

            } else {
              this.infoWorld = `${cityName} вже додано!`;
            }
            
          }
          console.log();

        })
        .catch(error => {
          console.error("Помилка:", error);
        });
    },
  }
}
</script>

<style scoped>
.oclock__program-title {
  font-size: 26px;
  margin-bottom: 20px;
}

.oclock__program-list {
  list-style: none;
}

.oclock__program-item {
  display: flex;
  padding: 20px 0;
  align-items: center;
  justify-content: space-between;
  border-top: 1px solid rgba(132, 132, 132, 0.3);
  border-bottom: 1px solid rgba(132, 132, 132, 0.3);
}

.oclock__program-item-left {
  display: flex;
  flex-direction: column;
  gap: 5px;
}

.oclock__program-top {
  font-size: 14px;
  color: #848484;
  /* margin-bottom: 5px; */
}

.oclock__program-bottom {
  font-size: 26px;
  font-weight: 300;
}

.oclock__program-time {
  font-size: 50px;
  font-weight: 300;
}

.oclock__program-menu {
  position: absolute;
  left: 0;
  right: 0;
  bottom: 20px;
  border-radius: 15px;
}

.clock__program-add {
  display: flex;
  flex-direction: column;
  position: absolute;
  left: 0;
  right: 0;
  top: 50%;
  transform: translateY(-50%);
}

.clock__program-input {
  background-color: transparent;
  border: none;
  outline: none;
  border-bottom: 1px solid #ff9f0a;
  width: 150px;
  margin: 0 auto 15px;
  color: #fff;
  font-size: 16px;
}

.clock__program-input::placeholder {
  color: #fff;
}

.clock__program-btn {
  width: 50px;
  text-align: center;
  margin: 0 auto;
  background-color: transparent;
  border: none;
  color: #fff;
  font-size: 16px;
  cursor: pointer;
  /* text-transform: uppercase; */
}

.clock__program-info {
  text-align: center;
}
</style>