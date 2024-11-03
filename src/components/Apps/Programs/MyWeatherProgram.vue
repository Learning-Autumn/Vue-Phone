<template>
  <div class="weather__program">
    <div v-if="!isLoading" class="weather__program-inner">
      <div class="weather__top">
        <p class="weather__top-title">My Location</p>
        <p class="weather__top-local">{{ locationCity }}</p>
        <p class="weather__top-temperature">{{ weatherData[0]?.avgTemperature }}°</p>
        <p class="weather__top-desp">Mostly Cloudy</p>
        <p class="weather__top-static">H:{{ weatherData[0]?.maxTemperature }}° L:{{ weatherData[0]?.minTemperature }}°
        </p>
      </div>

      <div class="weather__info">
        <p class="weather__info-text">
          Windy conditions from 01:00-07:00, with drizzle expected at 07:00.
        </p>
        <hr class="weather__section-line" />
        <ul class="weather__info-list">
          <li v-for="(day, index) in nextSixDays" :key="index" class="weather__info-item">
            <div class="weather__info-item-day">{{ day }}</div>

            <div class="weather__info-item-icon">☁️</div>
            <div class="weather__info-item-tempera">
              {{ weatherData[index]?.avgTemperature }}°
            </div>
          </li>
        </ul>
      </div>
      <div class="weather__detail">
        <p class="weather__detail-text">
          <svg class="weather__detail-text--icon" version="1.0" id="Layer_1" width="14px"
            xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 64 64"
            enable-background="new 0 0 64 64" xml:space="preserve" fill="#4d1d1d" stroke="#4d1d1d">
            <g id="SVGRepo_bgCarrier" stroke-width="0"></g>
            <g id="SVGRepo_tracerCarrier" stroke-linecap="round" stroke-linejoin="round"></g>
            <g id="SVGRepo_iconCarrier">
              <g>
                <path fill="#4f1d1d"
                  d="M11,54h6c0.553,0,1-0.447,1-1v-5c0-0.553-0.447-1-1-1h-6c-0.553,0-1,0.447-1,1v5C10,53.553,10.447,54,11,54 z M12,49h4v3h-4V49z">
                </path>
                <path fill="#4f1d1d"
                  d="M23,54h6c0.553,0,1-0.447,1-1v-5c0-0.553-0.447-1-1-1h-6c-0.553,0-1,0.447-1,1v5C22,53.553,22.447,54,23,54 z M24,49h4v3h-4V49z">
                </path>
                <path fill="#4f1d1d"
                  d="M35,54h6c0.553,0,1-0.447,1-1v-5c0-0.553-0.447-1-1-1h-6c-0.553,0-1,0.447-1,1v5C34,53.553,34.447,54,35,54 z M36,49h4v3h-4V49z">
                </path>
                <path fill="#4f1d1d"
                  d="M11,43h6c0.553,0,1-0.447,1-1v-5c0-0.553-0.447-1-1-1h-6c-0.553,0-1,0.447-1,1v5C10,42.553,10.447,43,11,43 z M12,38h4v3h-4V38z">
                </path>
                <path fill="#4f1d1d"
                  d="M23,43h6c0.553,0,1-0.447,1-1v-5c0-0.553-0.447-1-1-1h-6c-0.553,0-1,0.447-1,1v5C22,42.553,22.447,43,23,43 z M24,38h4v3h-4V38z">
                </path>
                <path fill="#4f1d1d"
                  d="M35,43h6c0.553,0,1-0.447,1-1v-5c0-0.553-0.447-1-1-1h-6c-0.553,0-1,0.447-1,1v5C34,42.553,34.447,43,35,43 z M36,38h4v3h-4V38z">
                </path>
                <path fill="#4f1d1d"
                  d="M47,43h6c0.553,0,1-0.447,1-1v-5c0-0.553-0.447-1-1-1h-6c-0.553,0-1,0.447-1,1v5C46,42.553,46.447,43,47,43 z M48,38h4v3h-4V38z">
                </path>
                <path fill="#4f1d1d"
                  d="M11,32h6c0.553,0,1-0.447,1-1v-5c0-0.553-0.447-1-1-1h-6c-0.553,0-1,0.447-1,1v5C10,31.553,10.447,32,11,32 z M12,27h4v3h-4V27z">
                </path>
                <path fill="#4f1d1d"
                  d="M23,32h6c0.553,0,1-0.447,1-1v-5c0-0.553-0.447-1-1-1h-6c-0.553,0-1,0.447-1,1v5C22,31.553,22.447,32,23,32 z M24,27h4v3h-4V27z">
                </path>
                <path fill="#4f1d1d"
                  d="M35,32h6c0.553,0,1-0.447,1-1v-5c0-0.553-0.447-1-1-1h-6c-0.553,0-1,0.447-1,1v5C34,31.553,34.447,32,35,32 z M36,27h4v3h-4V27z">
                </path>
                <path fill="#4f1d1d"
                  d="M47,32h6c0.553,0,1-0.447,1-1v-5c0-0.553-0.447-1-1-1h-6c-0.553,0-1,0.447-1,1v5C46,31.553,46.447,32,47,32 z M48,27h4v3h-4V27z">
                </path>
                <path fill="#4f1d1d"
                  d="M60,4h-7V3c0-1.657-1.343-3-3-3s-3,1.343-3,3v1H17V3c0-1.657-1.343-3-3-3s-3,1.343-3,3v1H4 C1.789,4,0,5.789,0,8v52c0,2.211,1.789,4,4,4h56c2.211,0,4-1.789,4-4V8C64,5.789,62.211,4,60,4z M49,3c0-0.553,0.447-1,1-1 s1,0.447,1,1v3v4c0,0.553-0.447,1-1,1s-1-0.447-1-1V6V3z M13,3c0-0.553,0.447-1,1-1s1,0.447,1,1v3v4c0,0.553-0.447,1-1,1 s-1-0.447-1-1V6V3z M62,60c0,1.104-0.896,2-2,2H4c-1.104,0-2-0.896-2-2V17h60V60z M62,15H2V8c0-1.104,0.896-2,2-2h7v4 c0,1.657,1.343,3,3,3s3-1.343,3-3V6h30v4c0,1.657,1.343,3,3,3s3-1.343,3-3V6h7c1.104,0,2,0.896,2,2V15z">
                </path>
              </g>
            </g>
          </svg>
          10-DAY FORECAST
        </p>
        <hr class="weather__section-line" />
        <ul class="weather__detail-list">
          <MyWeatherProgramSlider />
        </ul>
      </div>
    </div>
    <div v-else class="weather__program-loading">
      <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 100 100" preserveAspectRatio="xMidYMid" width="80"
        height="80" style="shape-rendering: auto; display: block; background: transparent;"
        xmlns:xlink="http://www.w3.org/1999/xlink">
        <g>
          <g transform="rotate(0 50 50)">
            <rect fill="#ffffff" height="12" width="6" ry="6" rx="3" y="24" x="47">
              <animate repeatCount="indefinite" begin="-0.9166666666666666s" dur="1s" keyTimes="0;1" values="1;0"
                attributeName="opacity"></animate>
            </rect>
          </g>
          <g transform="rotate(30 50 50)">
            <rect fill="#ffffff" height="12" width="6" ry="6" rx="3" y="24" x="47">
              <animate repeatCount="indefinite" begin="-0.8333333333333334s" dur="1s" keyTimes="0;1" values="1;0"
                attributeName="opacity"></animate>
            </rect>
          </g>
          <g transform="rotate(60 50 50)">
            <rect fill="#ffffff" height="12" width="6" ry="6" rx="3" y="24" x="47">
              <animate repeatCount="indefinite" begin="-0.75s" dur="1s" keyTimes="0;1" values="1;0"
                attributeName="opacity"></animate>
            </rect>
          </g>
          <g transform="rotate(90 50 50)">
            <rect fill="#ffffff" height="12" width="6" ry="6" rx="3" y="24" x="47">
              <animate repeatCount="indefinite" begin="-0.6666666666666666s" dur="1s" keyTimes="0;1" values="1;0"
                attributeName="opacity"></animate>
            </rect>
          </g>
          <g transform="rotate(120 50 50)">
            <rect fill="#ffffff" height="12" width="6" ry="6" rx="3" y="24" x="47">
              <animate repeatCount="indefinite" begin="-0.5833333333333334s" dur="1s" keyTimes="0;1" values="1;0"
                attributeName="opacity"></animate>
            </rect>
          </g>
          <g transform="rotate(150 50 50)">
            <rect fill="#ffffff" height="12" width="6" ry="6" rx="3" y="24" x="47">
              <animate repeatCount="indefinite" begin="-0.5s" dur="1s" keyTimes="0;1" values="1;0"
                attributeName="opacity"></animate>
            </rect>
          </g>
          <g transform="rotate(180 50 50)">
            <rect fill="#ffffff" height="12" width="6" ry="6" rx="3" y="24" x="47">
              <animate repeatCount="indefinite" begin="-0.4166666666666667s" dur="1s" keyTimes="0;1" values="1;0"
                attributeName="opacity"></animate>
            </rect>
          </g>
          <g transform="rotate(210 50 50)">
            <rect fill="#ffffff" height="12" width="6" ry="6" rx="3" y="24" x="47">
              <animate repeatCount="indefinite" begin="-0.3333333333333333s" dur="1s" keyTimes="0;1" values="1;0"
                attributeName="opacity"></animate>
            </rect>
          </g>
          <g transform="rotate(240 50 50)">
            <rect fill="#ffffff" height="12" width="6" ry="6" rx="3" y="24" x="47">
              <animate repeatCount="indefinite" begin="-0.25s" dur="1s" keyTimes="0;1" values="1;0"
                attributeName="opacity"></animate>
            </rect>
          </g>
          <g transform="rotate(270 50 50)">
            <rect fill="#ffffff" height="12" width="6" ry="6" rx="3" y="24" x="47">
              <animate repeatCount="indefinite" begin="-0.16666666666666666s" dur="1s" keyTimes="0;1" values="1;0"
                attributeName="opacity"></animate>
            </rect>
          </g>
          <g transform="rotate(300 50 50)">
            <rect fill="#ffffff" height="12" width="6" ry="6" rx="3" y="24" x="47">
              <animate repeatCount="indefinite" begin="-0.08333333333333333s" dur="1s" keyTimes="0;1" values="1;0"
                attributeName="opacity"></animate>
            </rect>
          </g>
          <g transform="rotate(330 50 50)">
            <rect fill="#ffffff" height="12" width="6" ry="6" rx="3" y="24" x="47">
              <animate repeatCount="indefinite" begin="0s" dur="1s" keyTimes="0;1" values="1;0" attributeName="opacity">
              </animate>
            </rect>
          </g>
          <g></g>
        </g>
      </svg>
    </div>
  </div>
</template>

<script>
import MyWeatherProgramSlider from "./MyWeatherProgramSlider.vue";

export default {
  inject: ["currentTimeData"],
  components: { MyWeatherProgramSlider },
  data() {
    return {
      weatherData: [],
      locationCity: "Kyiv",
      isLoading: true,
    };
  },
  created() {
    this.fetchWeatherData();
  },
  methods: {
    fetchWeatherData() {
      const today = new Date();
      const startDate = today.toISOString().split("T")[0];
      const endDate = new Date(today.setDate(today.getDate() + 5))
        .toISOString()
        .split("T")[0];

      const url = `https://api.open-meteo.com/v1/forecast?latitude=50.45&longitude=30.52&daily=temperature_2m_max,temperature_2m_min&timezone=Europe/Kiev&start_date=${startDate}&end_date=${endDate}`;

      fetch(url)
        .then((response) => {
          if (!response.ok) throw new Error("Не вдалося завантажити дані");
          return response.json();
        })
        .then((data) => {
          this.weatherData = data.daily.time.map((date, index) => {
            const maxTemp = data.daily.temperature_2m_max[index];
            const minTemp = data.daily.temperature_2m_min[index];
            const avgTemp = ((maxTemp + minTemp) / 2).toFixed(1);
            return {
              date,
              avgTemperature: avgTemp,
              minTemperature: minTemp,
              maxTemperature: maxTemp,
            };
          });
        })
        .finally(() => {
          this.isLoading = false;
        });
    },
  },
  computed: {
    daysInMonth() {
      const now = new Date();
      return new Date(now.getFullYear(), now.getMonth() + 1, 0).getDate();
    },
    nextSixDays() {
      const days = [];
      for (let i = 0; i < 6; i++) {
        let dayNumber = ((this.currentTimeData.dayNumber + i - 1) % this.daysInMonth) + 1;
        days.push(dayNumber < 10 ? "0" + String(dayNumber) : dayNumber);
      }
      return days;
    },
  },
};
</script>

<style scoped>
.weather__program {
  height: 700px;
  width: 328px;
  background-image: url("@/assets/images/weather_2.jpg");
  background-position: center;
  background-size: cover;
  border-radius: 50px;

  display: flex;
  align-items: center;
  flex-direction: column;
  justify-content: flex-end;
}

.weather__top {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  margin-bottom: 40px;
}

.weather__top-title {
  font-weight: 300;
  font-size: 32px;
}

.weather__top-local {
  text-transform: uppercase;
  font-size: 14px;
}

.weather__top-temperature {
  font-size: 80px;
  font-weight: 300;
}

.weather__top-static {
  font-weight: 300;
}

.weather__info,
.weather__detail {
  background: rgba(187, 87, 87, 0.7);
  border-radius: 30px;
  width: 300px;
  padding: 15px;
  margin: 0 auto 15px;
}

.weather__section-line {
  margin: 15px 0;
  border-color: rgb(119, 75, 108);
  width: 100%;
}

.weather__info-list {
  list-style: none;
}

.weather__info-text {
  font-weight: 300;
  font-size: 13px;
}

.weather__info-list {
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.weather__info-item {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 10px;
}

.weather__detail-text {
  font-size: 10px;
  display: flex;
  align-items: center;
  text-transform: uppercase;
  color: rgb(77, 29, 29);
}

.weather__detail-text--icon {
  margin-right: 10px;
}

.weather__detail-list {
  display: flex;
  flex-direction: column;
  align-items: center;
}

/* Slider CSS */
.weather__detail-item {
  display: flex;
  justify-content: space-between;
  align-items: center;
  width: 100%;
}

.weather__detail-nameDay {
  width: 45px;
}

.weather__detail-graph {
  display: flex;
  align-items: center;
  width: 150px;
}

.weather__detail-graph--box {
  width: 70px;
  height: 4px;
  position: relative;
  margin: 0 20px;
  background-color: rgba(0, 0, 0, 0.4);
  border-radius: 5px;
}

.weather__detail-graph--min {
  color: rgb(42, 35, 35);
}

.weather__detail-icon,
.weather__info-item-icon {
  font-size: 25px;
}

.weather__detail-graph--line {
  height: 4px;
  border-radius: 5px;
  background: rgb(67, 218, 255);
  background: linear-gradient(90deg,
      rgba(67, 218, 255, 1) 0%,
      rgba(160, 255, 149, 1) 100%);
}


.weather__program-loading {
  display: flex;
  height: 100%;
  align-items: center;
  justify-content: center;
}

/* <div class="weather__detail">
      <p class="weather__detail-text">
        10-DAY FORECAST
      </p>
      <hr>
      <ul class="weather__detail-list">
        <li class="weather__detail-item">
          <p class="weather__detail-nameDay">Today</p>
          <p class="weather__detail-img">SVG</p>
          <div class="weather__detail-graph">
            <p class="weather__detail-graph--min">8°</p>
            <div class="weather__detail-graph--line"></div>
            <p class="weather__detail-graph--max">14°</p>
          </div>
        </li>
      </ul>
    </div> */
</style>
