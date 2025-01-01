<template>
  <div class="oclock__slider-inner">
    <ul class="oclock__slider-list oclock__slider-list--left">
      <button
        class="alarms__slider-arrow"
        @click="showLeftPrev"
        :disabled="isLeftButtonDisabled"
      >
        <svg
          width="24px"
          height="24px"
          viewBox="0 0 24 24"
          fill="none"
          xmlns="http://www.w3.org/2000/svg"
        >
          <g id="SVGRepo_bgCarrier" stroke-width="0"></g>
          <g
            id="SVGRepo_tracerCarrier"
            stroke-linecap="round"
            stroke-linejoin="round"
          ></g>
          <g id="SVGRepo_iconCarrier">
            <path
              d="M18.2929 15.2893C18.6834 14.8988 18.6834 14.2656 18.2929 13.8751L13.4007 8.98766C12.6195 8.20726 11.3537 8.20757 10.5729 8.98835L5.68257 13.8787C5.29205 14.2692 5.29205 14.9024 5.68257 15.2929C6.0731 15.6835 6.70626 15.6835 7.09679 15.2929L11.2824 11.1073C11.673 10.7168 12.3061 10.7168 12.6966 11.1073L16.8787 15.2893C17.2692 15.6798 17.9024 15.6798 18.2929 15.2893Z"
              fill="#ff7a00"
            ></path>
          </g>
        </svg>
      </button>
      <VueSlickCarousel v-bind="settings_left" ref="carousel__left" :arrows="false">
        <li
          v-for="item in 24"
          @click="setSelectHour(item)"
          :key="item"
          class="oclock__slider-item"
        >
          {{ String(item).padStart(2, '0') }}
        </li>
      </VueSlickCarousel>
      <button
        class="alarms__slider-arrow"
        @click="showLeftNext"
        :disabled="isLeftButtonDisabled"
      >
        <svg
          width="24px"
          height="24px"
          viewBox="0 0 24 24"
          fill="none"
          xmlns="http://www.w3.org/2000/svg"
        >
          <g id="SVGRepo_bgCarrier" stroke-width="0"></g>
          <g
            id="SVGRepo_tracerCarrier"
            stroke-linecap="round"
            stroke-linejoin="round"
          ></g>
          <g id="SVGRepo_iconCarrier">
            <path
              d="M5.70711 9.71069C5.31658 10.1012 5.31658 10.7344 5.70711 11.1249L10.5993 16.0123C11.3805 16.7927 12.6463 16.7924 13.4271 16.0117L18.3174 11.1213C18.708 10.7308 18.708 10.0976 18.3174 9.70708C17.9269 9.31655 17.2937 9.31655 16.9032 9.70708L12.7176 13.8927C12.3271 14.2833 11.6939 14.2832 11.3034 13.8927L7.12132 9.71069C6.7308 9.32016 6.09763 9.32016 5.70711 9.71069Z"
              fill="#ff7a00"
            ></path>
          </g>
        </svg>
      </button>
    </ul>
    <ul class="oclock__slider-list oclock__slider-list--right">
      <button class="alarms__slider-arrow" @click="showRightPrev">
        <svg
          width="24px"
          height="24px"
          viewBox="0 0 24 24"
          fill="none"
          xmlns="http://www.w3.org/2000/svg"
        >
          <g id="SVGRepo_bgCarrier" stroke-width="0"></g>
          <g
            id="SVGRepo_tracerCarrier"
            stroke-linecap="round"
            stroke-linejoin="round"
          ></g>
          <g id="SVGRepo_iconCarrier">
            <path
              d="M18.2929 15.2893C18.6834 14.8988 18.6834 14.2656 18.2929 13.8751L13.4007 8.98766C12.6195 8.20726 11.3537 8.20757 10.5729 8.98835L5.68257 13.8787C5.29205 14.2692 5.29205 14.9024 5.68257 15.2929C6.0731 15.6835 6.70626 15.6835 7.09679 15.2929L11.2824 11.1073C11.673 10.7168 12.3061 10.7168 12.6966 11.1073L16.8787 15.2893C17.2692 15.6798 17.9024 15.6798 18.2929 15.2893Z"
              fill="#ff7a00"
            ></path>
          </g>
        </svg>
      </button>
      <VueSlickCarousel v-bind="settings_right" ref="carousel__right" :arrows="false">
        <li 
          v-for="item in 60"
          @click="setSelectMinutes(item)"
          :key="item" 
          class="oclock__slider-item"
        >
          {{ item }}
        </li>
      </VueSlickCarousel>
      <button class="alarms__slider-arrow" @click="showRightNext">
        <svg
          width="24px"
          height="24px"
          viewBox="0 0 24 24"
          fill="none"
          xmlns="http://www.w3.org/2000/svg"
        >
          <g id="SVGRepo_bgCarrier" stroke-width="0"></g>
          <g
            id="SVGRepo_tracerCarrier"
            stroke-linecap="round"
            stroke-linejoin="round"
          ></g>
          <g id="SVGRepo_iconCarrier">
            <path
              d="M5.70711 9.71069C5.31658 10.1012 5.31658 10.7344 5.70711 11.1249L10.5993 16.0123C11.3805 16.7927 12.6463 16.7924 13.4271 16.0117L18.3174 11.1213C18.708 10.7308 18.708 10.0976 18.3174 9.70708C17.9269 9.31655 17.2937 9.31655 16.9032 9.70708L12.7176 13.8927C12.3271 14.2833 11.6939 14.2832 11.3034 13.8927L7.12132 9.71069C6.7308 9.32016 6.09763 9.32016 5.70711 9.71069Z"
              fill="#ff7a00"
            ></path>
          </g>
        </svg>
      </button>
    </ul>
    <button @click="sendTimeToParent" class="alarms__add-btn" type="">Add</button>
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
      selectHour: 12,
      selectMinutes: 30,
      isLeftButtonDisabled: false,
      isRightButtonDisabled: false,
      settings_left: {
        infinite: true,
        slidesToShow: 1,
        slidesToScroll: 1,
        vertical: true,
        verticalSwiping: true,
        swipeToSlide: true,
        draggable: true,
        initialSlide: 11,
        centerMode: true,
        focusOnSelect: true,
      },
      settings_right: {
        infinite: true,
        slidesToShow: 1,
        slidesToScroll: 1,
        vertical: true,
        verticalSwiping: true,
        swipeToSlide: true,
        draggable: true,
        initialSlide: 29,
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
    setSelectMinutes(item) {
      this.selectMinutes = item;
      console.log("Selected Minutes:", this.selectMinutes);
    },
    setActive(index) {
      this.activeIndex = index;
    },
    showLeftNext() {
      if (!this.isLeftButtonDisabled) {
        this.$refs.carousel__left.next();
        if (this.selectHour < 24) {
          this.selectHour += 1;
        } else {
          this.selectHour = 1;
        }
        // console.log(this.selectHour);
        this.isLeftButtonDisabled = true;
        setTimeout(() => {
          this.isLeftButtonDisabled = false;
        }, 500);
      }
    },
    showLeftPrev() {
      if (!this.isLeftButtonDisabled) {
        this.$refs.carousel__left.prev();
        if (this.selectMinutes > 1) {
          this.selectHour -= 1;
        } else {
          this.selectHour = 24;
        }
        // console.log(this.selectHour);
        this.isLeftButtonDisabled = true;
        setTimeout(() => {
          this.isLeftButtonDisabled = false;
        }, 550);
      }
    },
    showRightNext() {
      if (!this.isLeftButtonDisabled) {
        this.$refs.carousel__right.next();
        if (this.selectMinutes < 60) {
          this.selectMinutes += 1;
        } else {
          this.selectMinutes = 1;
        }
        // console.log(this.selectMinutes);
        this.isLeftButtonDisabled = true;
        setTimeout(() => {
          this.isLeftButtonDisabled = false;
        }, 550);
      }
    },
    showRightPrev() {
      if (!this.isLeftButtonDisabled) {
        this.$refs.carousel__right.prev();
        if (this.selectMinutes < 60) {
          this.selectMinutes -= 1;
        } else {
          this.selectMinutes = 1;
        }
        // console.log(this.selectMinutes);
        this.isLeftButtonDisabled = true;
        setTimeout(() => {
          this.isLeftButtonDisabled = false;
        }, 550);
      }
    },
    sendTimeToParent(){
      let time = `${this.selectHour}:${this.selectMinutes}`
      this.$emit("addTime", time)
    }
  },
};
</script>

<style scoped>
.slick-current {
  color: #ff9f0a;
}

.oclock__slider-inner {
  position: relative;
  height: 490px;
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
  top: 50%;
  transform: translateY(-115%);
  width: 35px;
  right: 0;
  left: 0;
  margin: 0 auto;
  font-size: 50px;
  width: 65px;
  text-align: center;
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
  right: 70px;
  text-align: right;
}

.oclock__slider-list--right {
  left: 70px;
}
</style>
