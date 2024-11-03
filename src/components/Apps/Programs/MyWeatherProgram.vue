<template>
  <div class="weather__program">
    <div class="weather__top">
      <p class="weather__top-title">My Location</p>
      <p class="weather__top-local">{{ locationCity }}</p>
      <p class="weather__top-temperature">12°</p>
      <p class="weather__top-desp">Mostly Cloudy</p>
      <p class="weather__top-static">H:14° L:8°</p>
    </div>
    <div class="weather__info">
      <p class="weather__info-text">
        Windy conditions from 01:00-07:00, with
        drizzle expected at 07:00.
      </p>
      <hr class="weather__section-line">
      <ul class="weather__info-list">
        <li class="weather__info-item">
          <div class="weather__info-item-day">Now</div>
          <div class="weather__info-item-icon">☁️</div>
          <div class="weather__info-item-tempera">12°</div>
        </li>
        <li class="weather__info-item">
          <div class="weather__info-item-day">00</div>
          <div class="weather__info-item-icon">☁️</div>
          <div class="weather__info-item-tempera">12°</div>
        </li>
        <li class="weather__info-item">
          <div class="weather__info-item-day">01</div>
          <div class="weather__info-item-icon">🌫️</div>
          <div class="weather__info-item-tempera">12°</div>
        </li>
        <li class="weather__info-item">
          <div class="weather__info-item-day">02</div>
          <div class="weather__info-item-icon">🌫️</div>
          <div class="weather__info-item-tempera">11°</div>
        </li>
        <li class="weather__info-item">
          <div class="weather__info-item-day">03</div>
          <div class="weather__info-item-icon">🌫️</div>
          <div class="weather__info-item-tempera">11°</div>
        </li>
        <li class="weather__info-item">
          <div class="weather__info-item-day">04</div>
          <div class="weather__info-item-icon">🌫️</div>
          <div class="weather__info-item-tempera">11°</div>
        </li>
      </ul>
    </div>
    <div class="weather__detail">
      <p class="weather__detail-text">
        10-DAY FORECAST
      </p>
      <hr class="weather__section-line">
      <ul class="weather__detail-list">
        <li class="weather__detail-item">
          <p class="weather__detail-nameDay">Today</p>
          <p class="weather__detail-icon">☁️</p>
          <div class="weather__detail-graph">
            <p class="weather__detail-graph--min">8°</p>
            <div class="weather__detail-graph--box">
              <div class="weather__detail-graph--line" style="width: 30px; margin-left: 30px"></div>
            </div>
            <p class="weather__detail-graph--max">14°</p>
          </div>
        </li>
        <hr class="weather__section-line">
        <li class="weather__detail-item">
          <p class="weather__detail-nameDay">Sat</p>
          <p class="weather__detail-icon">🌧️</p>
          <div class="weather__detail-graph">
            <p class="weather__detail-graph--min">3°</p>
            <div class="weather__detail-graph--box">
              <div class="weather__detail-graph--line" style="width: 50px; margin-left: 10px"></div>
            </div>
            <p class="weather__detail-graph--max">12°</p>
          </div>
        </li>
        <hr class="weather__section-line">
        <li class="weather__detail-item">
          <p class="weather__detail-nameDay">Sun</p>
          <p class="weather__detail-icon">⛅</p>
          <div class="weather__detail-graph">
            <p class="weather__detail-graph--min">0°</p>
            <div class="weather__detail-graph--box">
              <div class="weather__detail-graph--line" style="width: 43px; margin-left: 8px"></div>
            </div>
            <p class="weather__detail-graph--max">6°</p>
          </div>
        </li>
        <!-- <hr class="weather__section-line"> -->
        <!-- <li class="weather__detail-item">
          <p class="weather__detail-nameDay">Mon</p>
          <p class="weather__detail-icon">🌫️</p>
          <div class="weather__detail-graph">
            <p class="weather__detail-graph--min">1°</p>
            <div class="weather__detail-graph--box">
              <div class="weather__detail-graph--line" style="width: 20px; margin-left: 35px"></div>
            </div>
            <p class="weather__detail-graph--max">8°</p>
          </div>
        </li>
        <hr class="weather__section-line"> -->
      </ul>
    </div>
    <!-- <div v-if="weatherData">
      <p>Температура (щогодини):</p>
      <ul>
        <li v-for="(temp, index) in weatherData" :key="index">
          {{ index }}:00 - {{ temp }}°C
        </li>
      </ul>
    </div> -->
  </div>
</template>

<script>
export default {
  data() {
    return {
      weatherData: null,
      locationCity: 'Kyiv',
    };
  },
  created() {
    this.fetchWeatherData();
  },
  methods: {
    fetchWeatherData() {
      const today = new Date();
      const startDate = today.toISOString().split('T')[0];
      const endDate = new Date(today.setDate(today.getDate() + 5)).toISOString().split('T')[0];

      const url = `https://api.open-meteo.com/v1/forecast?latitude=50.45&longitude=30.52&daily=temperature_2m_max,temperature_2m_min&timezone=Europe/Kiev&start_date=${startDate}&end_date=${endDate}`;

      fetch(url)
        .then(response => {
          if (!response.ok) throw new Error('Не вдалося завантажити дані');
          return response.json();
        })
        .then(data => {
          this.weatherData = data.daily.time.map((date, index) => {
            const maxTemp = data.daily.temperature_2m_max[index];
            const minTemp = data.daily.temperature_2m_min[index];
            const avgTemp = ((maxTemp + minTemp) / 2).toFixed(1);
            return {
              date,
              avgTemperature: avgTemp
            };
          });
        })
    }
  }
};
</script>

<style scoped>
.weather__program {
  height: 700px;
  width: 328px;
  background-image: url('@/assets/images/weather_2.jpg');
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
  text-transform: uppercase;
  color: rgb(77, 29, 29);
}

.weather__detail-list {
  display: flex;
  flex-direction: column;
  align-items: center;
}

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
  background: linear-gradient(90deg, rgba(67, 218, 255, 1) 0%, rgba(160, 255, 149, 1) 100%);
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
