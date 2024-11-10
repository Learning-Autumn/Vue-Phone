<template>
  <div class="oclock__stopwatch">
    <p class="oclock__stop">00:00,00</p>
    <div class="oclock__control">
      <button class="oclock__control-btn oclock__control-btn--left" type="">Lap</button>
      <div>
        .
      </div>
      <button class="oclock__control-btn oclock__control-btn--right" type="">Start</button>
    </div>
  </div>
</template>

<script>
  export default {
    
  }
</script>

<style scoped>
.oclock__stopwatch {
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
  height: 100%;
  padding-bottom: 120px;
}
.oclock__stop {
  font-size: 76px;
  font-weight: 300;
  margin-bottom: 80px;
}
.oclock__control {
  display: flex;
  justify-content: space-between;
  align-items: center;
  width: 100%;
  padding: 0 15px;
}
.oclock__control-btn {
  width: 70px;
  height: 70px;
  border-radius: 50%;
  cursor: pointer;
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

</style>