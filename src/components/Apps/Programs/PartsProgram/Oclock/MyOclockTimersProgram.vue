<template>
  <div class="oclock__timers">
    <h2 class="oclock__program-title">Timers</h2>

    <div class="oclock__control">
      <button class="oclock__control-btn oclock__control-btn--left" type="">Lap</button>
      <div>.</div>
      <button class="oclock__control-btn oclock__control-btn--right" type="">
        Start
      </button>
    </div>

    <div class="oclock__desc">
      <ul class="oclock__desc-list">
        <li class="oclock__desc-item">
          <p class="oclock__desc-item-title">Назва</p>
          <p class="oclock__desc-item-title">Таймер</p>
        </li>
        <hr class="oclock__desc-line" />
        <li class="oclock__desc-item">
          <p class="oclock__desc-item-title">У кінці</p>
          <p class="oclock__desc-item-title">Качка</p>
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {};
</script>

<style scoped>
.oclock__program-title {
  margin-top: 38px;
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

.oclock__desc-item {
  display: flex;
  justify-content: space-between;
}

.oclock__desc-line {
  border-top-color: #28282a;
}
</style>
