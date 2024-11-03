<template>
  <div class="map__program" id="map" style="height: 700px; width: 328px" ></div>
</template>

<script>
import L from 'leaflet';
import 'leaflet/dist/leaflet.css';

export default {
  name: 'MapComponent',
  data() {
    return {
      map: null,
    };
  },
  mounted() {
    this.map = L.map('map', { zoomControl: false }).setView([50.4501, 30.5234], 13); 

    L.tileLayer('https://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png', {
      maxZoom: 19,
      attribution:
        '&copy; <a href="https://www.openstreetmap.org/copyright">OpenStreetMap</a> contributors',
    }).addTo(this.map);

    // Додавання маркера
    // L.marker([51.505, -0.09])
    //   .addTo(this.map)
    //   .bindPopup('Це тестовий маркер.')
    //   .openPopup();
  },
};
</script>

<style>
#map {
  width: 100%;
  height: 100%;
}

.map__program {
  border-radius: 50px;
}
</style>
