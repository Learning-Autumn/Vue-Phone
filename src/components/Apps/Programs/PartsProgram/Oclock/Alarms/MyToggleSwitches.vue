<template>
  <div @click="toggleSwitches" class="toggleSwitches__container">
    <div  :class="['toggleSwitches__circle', { active: isLocalActive }]">
    </div>
  </div>
</template>
<script>
export default {
  data() {
    return {
      isLocalActive: this.isActive,
    }
  },
  props: {
    isActive: {
      type: Boolean,
      require: true,
    }
  },
  methods: {
    toggleSwitches(){
      this.isLocalActive = !this.isLocalActive
      this.$emit('toggleSwitches', this.isLocalActive)
    }
  },
}
</script>
<style scoped>
.toggleSwitches__container {
  width: 50px;
  background-color: #262628;
  height: 28px;
  border-radius: 30px;
  position: relative;
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 2px;
}
.toggleSwitches__circle {
  position: absolute;
  width: 26px;
  height: 26px;
  border-radius: 50%;
  background-color: #848484;

  transition: transform 0.3s ease;

}
.toggleSwitches__circle.active {
  transform: translateX(22px); 
  background-color: #fff;

}
</style>