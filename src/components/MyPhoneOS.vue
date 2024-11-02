<template>
  <div class="os__inner" v-if="isOpen && isLoads">
    <MyLockScreen v-if="!isUnlocked" :toggleUnlock="toggleUnlock" />
    <MyWorkDesk v-else />
  </div>
</template>

<script>
import Vue from "vue";
import MyLockScreen from "./MyLockScreen.vue";
import MyWorkDesk from "./MyWorkDesk.vue";

const currentTimeData = Vue.observable({
  currentTime: "",
  dayNumber: null,
  dayName: "",
  monthNumber: null,
  monthName: "",
});
export default {
  components: {
    MyLockScreen,
    MyWorkDesk,
  },
  data() {
    return {
      isUnlocked: true,
      currentDate: new Date(),
    };
  },
  props: {
    isOpen: {
      type: Boolean,
      required: true,
    },
    isLoads: {
      type: Boolean,
      required: true,
    },
  },
  methods: {
    toggleUnlock() {
      this.isUnlocked = !this.isUnlocked;
    },
    setUnlocked(value) {
      this.isUnlocked = value;
    },
    updateTime() {
      const now = new Date();
      currentTimeData.currentTime = `${String(now.getHours()).padStart(2, "0")}:${String(
        now.getMinutes()
      ).padStart(2, "0")}`;

      this.currentDate = now;

      // Оновлюємо номер і назву дня
      currentTimeData.dayNumber = now.getDate(); // Номер дня (0-6, де 0 - неділя)
      const days = [
        "Неділя",
        "Понеділок",
        "Вівторок",
        "Середа",
        "Четвер",
        "П’ятниця",
        "Субота",
      ];
      currentTimeData.dayName = days[now.getDay()];

      currentTimeData.monthNumber = now.getMonth() + 1;
      const months = [
        "січня",
        "лютого",
        "березня",
        "квітня",
        "травня",
        "червня",
        "липня",
        "серпня",
        "вересня",
        "жовтня",
        "листопада",
        "грудня",
      ];
      currentTimeData.monthName = months[now.getMonth()]; // Назва місяця
    },
  },
  computed: {
    currentTime() {
      const hours = String(this.currentDate.getHours()).padStart(2, "0");
      const minutes = String(this.currentDate.getMinutes()).padStart(2, "0");

      return `${hours}:${minutes}`;
    },
    getFormattedDate() {
      const day = this.currentDate.getDate();
      return `${currentTimeData.dayName}, ${day} ${currentTimeData.monthName}`; // Формат дати
    },
  },
  mounted() {
    this.updateTime();
    setInterval(() => {
      this.currentDate = new Date();
      this.updateTime();
    }, 60000);
  },
  provide() {
    return {
      currentTimeData,
    };
  },
};
</script>

<style scoped>
.os__inner {
  position: absolute;
  height: 695px;
  display: flex;
  justify-content: center;
  align-items: center;
  top: 80px;
  width: 320px;
}
</style>
