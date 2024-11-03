<template>
  <div class="slider-container">
    <button class="weather__slider-arrow" @click="showPrev">
      <svg
        width="20px"
        height="20px"
        viewBox="0 0 24 24"
        fill="none"
        xmlns="http://www.w3.org/2000/svg"
      >
        <g id="SVGRepo_bgCarrier" stroke-width="0"></g>
        <g id="SVGRepo_tracerCarrier" stroke-linecap="round" stroke-linejoin="round"></g>
        <g id="SVGRepo_iconCarrier">
          <path
            d="M18.2929 15.2893C18.6834 14.8988 18.6834 14.2656 18.2929 13.8751L13.4007 8.98766C12.6195 8.20726 11.3537 8.20757 10.5729 8.98835L5.68257 13.8787C5.29205 14.2692 5.29205 14.9024 5.68257 15.2929C6.0731 15.6835 6.70626 15.6835 7.09679 15.2929L11.2824 11.1073C11.673 10.7168 12.3061 10.7168 12.6966 11.1073L16.8787 15.2893C17.2692 15.6798 17.9024 15.6798 18.2929 15.2893Z"
            fill="#4f1d1d"
          ></path>
        </g>
      </svg>
    </button>
    <vue-slick-carousel
      ref="carousel"
      :dots="false"
      :arrows="false"
      :slidesToShow="3"
      :slidesToScroll="1"
      :vertical="true"
      :infinite="false"
      :verticalSwiping="true"
      class="horizontal-slider"
    >
      <li
        v-for="(item, index) in functions"
        :key="index"
        class="weather__detail-item"
        @click="setActive(index)"
      >
        <p class="weather__detail-nameDay">{{ item.dayName }}</p>
        <p class="weather__detail-icon">{{ item.weatherIcon }}</p>
        <div class="weather__detail-graph">
          <p class="weather__detail-graph--min">{{ item.minTemperature }}°</p>
          <div class="weather__detail-graph--box">
            <div
              class="weather__detail-graph--line"
              style="width: 30px; margin-left: 30px"
            ></div>
          </div>
          <p class="weather__detail-graph--max">{{ item.maxTemperature }}°</p>
          <hr class="weather__section-line" />
        </div>
      </li>
    </vue-slick-carousel>
    <button class="weather__slider-arrow" @click="showNext">
      <svg
        width="20px"
        height="20px"
        viewBox="0 0 24 24"
        fill="none"
        xmlns="http://www.w3.org/2000/svg"
      >
        <g id="SVGRepo_bgCarrier" stroke-width="0"></g>
        <g id="SVGRepo_tracerCarrier" stroke-linecap="round" stroke-linejoin="round"></g>
        <g id="SVGRepo_iconCarrier">
          <path
            d="M5.70711 9.71069C5.31658 10.1012 5.31658 10.7344 5.70711 11.1249L10.5993 16.0123C11.3805 16.7927 12.6463 16.7924 13.4271 16.0117L18.3174 11.1213C18.708 10.7308 18.708 10.0976 18.3174 9.70708C17.9269 9.31655 17.2937 9.31655 16.9032 9.70708L12.7176 13.8927C12.3271 14.2833 11.6939 14.2832 11.3034 13.8927L7.12132 9.71069C6.7308 9.32016 6.09763 9.32016 5.70711 9.71069Z"
            fill="#4f1d1d"
          ></path>
        </g>
      </svg>
    </button>
  </div>
</template>

<script>
import VueSlickCarousel from "vue-slick-carousel";
import "vue-slick-carousel/dist/vue-slick-carousel.css";

export default {
  components: { VueSlickCarousel },
  data() {
    return {
      functions: [
        {
          dayName: "Today",
          weatherIcon: "☁️",
          minTemperature: 8,
          maxTemperature: 14,
        },
        {
          dayName: "Today",
          weatherIcon: "☁️",
          minTemperature: 8,
          maxTemperature: 14,
        },
        {
          dayName: "Today",
          weatherIcon: "☁️",
          minTemperature: 8,
          maxTemperature: 14,
        },
        {
          dayName: "Today",
          weatherIcon: "☁️",
          minTemperature: 8,
          maxTemperature: 14,
        },
        {
          dayName: "Today",
          weatherIcon: "☁️",
          minTemperature: 8,
          maxTemperature: 14,
        },
        {
          dayName: "Today",
          weatherIcon: "☁️",
          minTemperature: 8,
          maxTemperature: 14,
        },
        {
          dayName: "Today",
          weatherIcon: "☁️",
          minTemperature: 8,
          maxTemperature: 14,
        },
      ],
    };
  },
  methods: {
    setActive(index) {
      this.activeIndex = index;
    },
    showNext() {
      this.$refs.carousel.next();
    },
    showPrev() {
      this.$refs.carousel.prev();
    },
  },
};
</script>

<style>
.slider-container {
  max-width: 280px;
  overflow-y: hidden;
}

.weather__detail-item {
  display: inline-flex !important;
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
  background: linear-gradient(
    90deg,
    rgba(67, 218, 255, 1) 0%,
    rgba(160, 255, 149, 1) 100%
  );
}

.weather__slider-arrow {
  background-color: transparent;
  border: none;
  cursor: pointer;
}
</style>
