<template>
  <div class="oclock__program-inner">
    <p class="oclock__control-text">
      Edit
    </p>
    <p class="oclock__control-add" @click="handleAddClick">
      +
    </p>
  </div>
</template>

<script>
export default {
  props: {
    parentId: {
      type: String,
      required: true,
    }
  },
  methods: {
    handleAddClick() {   
      this.$emit('add-click', this.parentId)
    }
  }
}
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
}

.oclock__control-add {
  font-size: 28px;
  cursor: pointer;
}
</style>