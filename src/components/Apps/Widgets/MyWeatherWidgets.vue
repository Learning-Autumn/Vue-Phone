<template>
  <div @click="openApp" class="work__desp-widget--weather">
    <p class="work__widget-local">Київ</p>
    <p class="work__widget-temper">{{weatherData[0].avgTemperature}}°</p>
    <p class="work__widget-status">Сонячно</p>
    <p class="work__widget-desp">B:{{weatherData[0].maxTemperature}}° H:{{weatherData[0].minTemperature}}°</p>
  </div>
</template>

<script>
export default {
  inject: ['setProgram'],
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
    openApp() {
      this.setProgram('WeatherWidgets');
    },
    fetchWeatherData() {
      const todayDate = new Date().toISOString().split("T")[0]; // Сьогоднішня дата

      const url = `https://api.open-meteo.com/v1/forecast?latitude=50.45&longitude=30.52&daily=temperature_2m_max,temperature_2m_min&timezone=Europe/Kiev&start_date=${todayDate}&end_date=${todayDate}`;

      fetch(url)
        .then((response) => {
          if (!response.ok) throw new Error("Не вдалося завантажити дані");
          return response.json();
        })
        .then((data) => {
          if (data.daily.time.length > 0) {
            const maxTemp = data.daily.temperature_2m_max[0];
            const minTemp = data.daily.temperature_2m_min[0];
            const avgTemp = ((maxTemp + minTemp) / 2).toFixed(1);
            this.weatherData.push({
              date: data.daily.time[0],
              avgTemperature: avgTemp,
              minTemperature: minTemp,
              maxTemperature: maxTemp,
            });
          }
        })
        .finally(() => {
          this.isLoading = false;
        });
    },
  }
}
</script>

<style scoped>
.work__desp-widget--weather {
  background: rgb(41, 41, 200);
  background: linear-gradient(180deg, rgba(41, 41, 200, 1) 0%, rgba(0, 212, 255, 1) 100%);
}

.work__widget-local {
  font-weight: normal;
  margin-bottom: 5px;
}

.work__widget-temper {
  font-size: 35px;
  margin-bottom: 25px;
}

.work__widget-status {
  font-size: 12px;
}

.work__widget-desp {
  font-size: 12px;
}
</style>