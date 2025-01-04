<template>
  <div class="app" id="app">
    <MyPhone />
  </div>
</template>

<script>
import MyPhone from "./components/MyPhone.vue";

export default {
  name: "App",
  components: {
    MyPhone,
  },
};
</script>

<style>
.app {
  background-color: #8792d15e;
  min-height: 100vh;
  padding-bottom: 50px;
}

.container {
  padding: 0 15px;
  margin: 0 auto;
  max-width: 1250px;
}
</style>
