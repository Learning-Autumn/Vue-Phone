<template>
  <div>
    <h2 class="oclock__program-title">
      World Clock
    </h2>
    <ul class="woclock__program-list">
      <li class="oclock__program-item">
        <div class="woclock__program-item-left">
          <p class="oclock__program-top">Today, +0HRS</p>
          <p class="oclock__program-bottom">Kyiv</p>
        </div>
        <div class="oclock__program-item-right">
          <p class="oclock__program-time">23:30</p>
        </div>
      </li>
    </ul>
  </div>
</template>

<script>
export default {

}
</script>

<style scoped>

.oclock__program-title {
  font-size: 26px;
  margin-bottom: 20px;
}

.oclock__program-list {
  list-style: none;
}

.oclock__program-item {
  display: flex;
  padding: 20px 0;
  align-items: center;
  justify-content: space-between;
  border-top: 1px solid rgba(132, 132, 132, 0.3);
  border-bottom: 1px solid rgba(132, 132, 132, 0.3);
}

.oclock__program-item-left {
  display: flex;
  flex-direction: column;
  gap: 5px;
}

.oclock__program-top {
  font-size: 14px;
  color: #848484;
  /* margin-bottom: 5px; */
}

.oclock__program-bottom {
  font-size: 26px;
  font-weight: 300;
}

.oclock__program-time {
  font-size: 50px;
  font-weight: 300;
}

.oclock__program-menu {
  position: absolute;
  left: 0;
  right: 0;
  bottom: 20px;
}
</style>