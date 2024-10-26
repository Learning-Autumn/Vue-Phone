<template>
  <div class="app" id="app">
    <AppCalculator />
  </div>
</template>

<script>
import AppCalculator from "./components/MyPhone.vue";

export default {
  name: "App",
  components: {
    AppCalculator,
  },
};
</script>

<style>
.app {
  background-color: #8792d15e;
}

.container {
  padding: 0 15px;
  margin: 0 auto;
  max-width: 1250px;
}
</style>
