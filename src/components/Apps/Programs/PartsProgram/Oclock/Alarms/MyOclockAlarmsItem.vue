<template>
  <li :class="['oclock__program-item', {active: isLocalActive}]" > 
    <div class="oclock__program-item-left">
      <p class="oclock__program-bottom">{{Time}}</p>
      <p class="oclock__program-top">Alarm</p>
    </div>
    <div class="oclock__program-item-right">
      <MyToggleSwitches @toggleSwitches="toggleItem" :isActive="isActive"/>
    </div>
  </li>
</template>

<script>
import MyToggleSwitches from './MyToggleSwitches.vue';


export default {
  components: { MyToggleSwitches },
  data() {
    return {
      isLocalActive: this.isActive,
    }
  },
  props: {
    Time: {
      type: String,
      required: true,
    },
    isActive: {
      type: Boolean,
      require: true,
    }
  },
  methods: {
    toggleItem(status){
      this.isLocalActive = status 
    }
  }
}
</script>

<style scoped>
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
  color: #848484;
  font-weight: 300;
  transition: all .1s;
}

.oclock__program-item.active .oclock__program-item-left{
  color: #fff;
}

.oclock__program-top {
  font-size: 14px;
  /* margin-bottom: 5px; */
}

.oclock__program-bottom {
  font-size: 45px;
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