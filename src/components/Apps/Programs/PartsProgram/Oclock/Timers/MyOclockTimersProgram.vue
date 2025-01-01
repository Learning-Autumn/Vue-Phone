<template>
  <div class="oclock__timers">

    <div class="oclock__program-inner">
      <p class="oclock__control-text">
        Edit
      </p>
    </div>

    <h2 class="oclock__program-title">Timers</h2>

    <div class="oclock__edit">
      <MyOclockTimersSlider></MyOclockTimersSlider>
    </div>

    <div class="oclock__control">
      <button class="oclock__control-btn oclock__control-btn--left" type="">
        Cancel
      </button>
      <button class="oclock__control-btn oclock__control-btn--right" type="">
        Start
      </button>
    </div>

    <div class="oclock__desc">
      <ul class="oclock__desc-list">
        <li class="oclock__desc-item">
          <p class="oclock__desc-item-title">Label</p>
          <p class="oclock__desc-item-title oclock__desc-item-title--timer">Timer</p>
        </li>
        <hr class="oclock__desc-line" />
        <li class="oclock__desc-item">
          <p class="oclock__desc-item-title">When Timer Ends</p>
          <p class="oclock__desc-item-title">Radial</p>
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
import MyOclockTimersSlider from "./MyOclockTimersSlider.vue";

export default {
  components: { MyOclockTimersSlider }
};
</script>

<style scoped>
.oclock__program-inner {
  display: flex;
  justify-content: space-between;
  color: #ff9f0a;
  font-size: 16px;
  display: flex;
  align-items: center;
  font-weight: 300;
  margin-bottom: 10px;
  height: 28px;
}

.oclock__program-title {
  font-size: 26px;
  margin-bottom: 20px;
}

.oclock__control-btn {
  width: 70px;
  height: 70px;
  border-radius: 50%;
  cursor: pointer;
  margin-bottom: 25px;
}

.oclock__control {
  display: flex;
  justify-content: space-between;
  align-items: center;
  width: 100%;
  padding: 0 15px;
}

.oclock__control-btn--left {
  background-color: #1c1c1e;
  border: none;
  color: #848484;
}
.oclock__control-btn--right {
  background-color: #092911;
  border: none;
  color: #5dcb85;
}

.oclock__desc {
  display: flex;
  flex-direction: column;
  background-color: #1c1c1e;
  border-radius: 15px;
  padding: 15px;
  font-size: 13px;
}

.oclock__desc-list {
  font-size: 14.5px;
}

.oclock__desc-item {
  display: flex;
  justify-content: space-between;
}

.oclock__desc-line {
  border-top-color: #28282a;
}

.oclock__desc-item-title--timer {
  color: #848484;
}
</style>
