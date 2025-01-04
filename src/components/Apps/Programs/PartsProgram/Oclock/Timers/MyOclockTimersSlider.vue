<template>
  <div class="oclock__slider-inner">
    <div class="oclock__slider-hide"></div>
    <div class="oclock__slider-selected">
      <p class="oclock__slider-selected--desc oclock__slider-selected--left">hours</p>
      <p class="oclock__slider-selected--desc oclock__slider-selected--center">min</p>
      <p class="oclock__slider-selected--desc oclock__slider-selected--right">sec</p>
    </div>
    <ul class="oclock__slider-list oclock__slider-list--left">
      <VueSlickCarousel v-bind="settings_left" ref="carousel__left" :arrows="false">
        <li
          v-for="item in Array.from({length: 24}, (_, index) => index)"
          @click="setSelectHour(item)"
          :key="item"
          class="oclock__slider-item"
        >
          {{ item }}
        </li>
      </VueSlickCarousel>
    </ul>
    <ul class="oclock__slider-list oclock__slider-list--center">
      <VueSlickCarousel v-bind="settings_right" ref="carousel__center" :arrows="false">
        <li 
          v-for="item in Array.from({length: 60}, (_, index) => index)" 
          @click="setSelectMinute(item)"
          :key="item" 
          class="oclock__slider-item"
        >
          {{ item }}
        </li>
      </VueSlickCarousel>
    </ul>
    <ul class="oclock__slider-list oclock__slider-list--right">
      <VueSlickCarousel v-bind="settings_right" ref="carousel__right" :arrows="false">
        <li 
          v-for="item in Array.from({length: 60}, (_, index) => index)"
          @click="setSelectSecond(item)"
          :key="item" 
          class="oclock__slider-item"
        >
          {{ item }}
        </li>
      </VueSlickCarousel>
    </ul>
  </div>
</template>

<script>
import VueSlickCarousel from "vue-slick-carousel";
import "vue-slick-carousel/dist/vue-slick-carousel.css";
// optional style for arrows & dots
import "vue-slick-carousel/dist/vue-slick-carousel-theme.css";

export default {
  name: "MyComponent",
  components: { VueSlickCarousel },
  data() {
    return {
      selectHour: 0,
      selectMinutes: 0,
      selectSecond: 0,
      isLeftButtonDisabled: false,
      isRightButtonDisabled: false,
      settings_left: {
        infinite: false,
        slidesToShow: 1,
        slidesToScroll: 1,
        vertical: true,
        verticalSwiping: true,
        swipeToSlide: true,
        draggable: true,
        initialSlide: 0,
        centerMode: true,
        focusOnSelect: true,
      },
      settings_center: {
        infinite: false,
        slidesToShow: 1,
        slidesToScroll: 1,
        vertical: true,
        verticalSwiping: true,
        swipeToSlide: true,
        draggable: true,
        initialSlide: 0,
        centerMode: true,
        focusOnSelect: true,
      },
      settings_right: {
        infinite: false,
        slidesToShow: 1,
        slidesToScroll: 1,
        vertical: true,
        verticalSwiping: true,
        swipeToSlide: true,
        draggable: true,
        initialSlide: 0,
        centerMode: true,
        focusOnSelect: true,
      },
    };
  },
  methods: {
    setSelectHour(item) {
      this.selectHour = item;
      console.log("Selected Hour:", this.selectHour);
    },
    setSelectMinute(item) {
      this.selectMinutes = item;
      console.log("Selected Minute:", this.selectMinutes);
    },
    setSelectSecond(item) {
      this.selectSecond = item;
      console.log("Selected Second:", this.selectSecond);
    },
    setActive(index) {
      this.activeIndex = index;
    },
    addTimerData(){
      let timerMinutes = String(this.selectMinutes).padStart(2, '0')
      let timerSeconds = String(this.selectSecond).padStart(2, '0')

      const timer = {
        'Time': {
          'minutes': timerMinutes,
          'seconds': timerSeconds,
        },
        'TimeLeft': {
          'minutes': timerMinutes,
          'seconds': timerSeconds,
        },
        'isActive': true,
      }
      
      return timer
    }
  },
};
</script>

<style scoped>
.slick-current {
  color: #ff9f0a;
}

.oclock__slider-inner {
  height: 190px;
  position: relative;
}

.alarms__slider-arrow {
  background-color: transparent;
  border: none;
  padding: 0;
  margin: 0 auto;
  width: 100%;
}

.oclock__slider-list {
  position: absolute;
  top: 40px;
  /* transform: translateY(-115%); */
  width: 35px;
  right: 0;
  left: 0;
  margin: 0 auto;
  font-size: 20px;
  line-height: 30px;
  width: 65px;
  text-align: center;
}

.oclock__slider-item {
  transform: rotateX(-30deg);
  perspective: 500px;
  transform-origin: center;
  display: inline-block;
  transition: transform 0.3s ease-in-out;
}

.oclock__slider-item:hover {
  transform: rotateX(0deg) scale(1.2);
}


.oclock__slider-selected {
  width: 240px;
  background: #1c1c1e;
  height: 26px;
  position: absolute;
  top: 50%;
  border-radius: 5px;
  transform: translateY(-2px);
  margin: 0 auto;
  left: 0;
  right: 0;
  position: relative;

}

.oclock__slider-selected--desc {
  position: absolute;
  top: 50%;
  transform: translateY(-50%);
}


.oclock__slider-selected--left {
  left: 50px;
}

.oclock__slider-selected--center {
  left: 132px;
}

.oclock__slider-selected--right {
  right: 10px;
}

.oclock__slider-hide {
  width: 240px;
  background: black;
  z-index: 10;
  height: 53px;
  position: absolute;
  top: 50px;
  border-radius: 5px;
  transform: translateY(-10px);
  margin: 0 auto;
  left: 0;
  right: 0;
}

.alarms__add-btn {
  position: absolute;
  top: 50%;
  left: 0;
  right: 0;
  width: 80px;
  background-color: transparent;
  color: white;
  margin: 0 auto;
  border: 1px solid #fff;
  padding: 5px 18px;
  display: inline-block;
  border-radius: 10px;
}

.slick-slider {
  text-align: center;
}

.oclock__slider-list--left {
  right: 165px;
  text-align: right;
}

.oclock__slider-list--right {
  /* left: 70px; */
}

.oclock__slider-list--right {
  left: 150px;
}
</style>
