<template>
  <div class="slider-container">
    <vue-slick-carousel 
      :dots="false" 
      :arrows="false" 
      :slidesToShow="3" 
      :slidesToScroll="1"
      :centerMode="true" 
      :focusOnSelect="true"
      :infinite="false" 
      :initialSlide="2" 
      class="horizontal-slider"
    >
      <div v-for="(item, index) in functions" 
           :key="index" 
           :class="['camera_interface-function', { 'camera_interface-function--active': index === activeIndex, 'camera_interface-function--left': index === 0, 'camera_interface-function--right': index === functions.length - 1 }]"
           @click="setActive(index)"
      >
        {{ item }}
      </div>
    </vue-slick-carousel>
  </div>
</template>

<script>
import VueSlickCarousel from 'vue-slick-carousel'
import 'vue-slick-carousel/dist/vue-slick-carousel.css'

export default {
  components: { VueSlickCarousel },
  data() {
    return {
      functions: ['Пагрограф', 'Відео', 'Фото', 'Портрет', 'Панорама'],
      activeIndex: 2 // Початково активний третій елемент (індекс 2)
    }
  },
  methods: {
    setActive(index) {
      this.activeIndex = index
    }
  }
}
</script>

<style>
.slider-container {
  width: 300px;
  margin: 0 auto 18px; 
}

.horizontal-slider .slick-track {
  display: flex;
  align-items: center;
}

.camera_interface-function {
  text-align: center;
  cursor: pointer;
  font-size: 13px;
  text-transform: uppercase;
}

.camera_interface-function--active {
  color: #ffee60; 
}
.camera_interface-function--left {
  transform: rotateY(-30deg); /* Повертаємо лівий елемент */
}

.camera_interface-function--right {
  transform: rotateY(30deg); /* Повертаємо правий елемент */
}
</style>
