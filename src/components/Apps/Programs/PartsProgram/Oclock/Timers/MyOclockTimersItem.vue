<template>
  <li class="oclock__program-item">
    {{ isActive }}
    <div class="oclock__program-item-left">
      <p class="oclock__program-item-time">{{ Time }}</p>
    </div>
    <div class="oclock__program-item-right">
      <button class="oclock__program-item-start"></button>
      <button class="oclock__program-item-pause"></button>
    </div>
  </li>
</template>

<script>
  export default {
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
  }
</script>

<style lang="scss" scoped>

</style>