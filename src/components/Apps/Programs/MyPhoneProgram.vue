<template>
  <div class="phone__programs">
    <div v-if="currentMenu === 'KeyPad'" class="phone__program">
      <MyPhoneKeypadProgram/>
    </div>
    <div v-if="currentMenu === 'Recents'" class="phone__program">
      <MyPhoneRecentsProgram/>
    </div>
    <div v-if="currentMenu === 'VoiceMail'" class="phone__program">
      <MyPhoneVoiceMailProgram/>
    </div>
    <MyPhoneMenu class="phone__programs-menu" :isOpenMenu="currentMenu" @changeMenu="updateCurrentMenu"/>
  </div>
</template>

<script>
import MyPhoneKeypadProgram from './PartsProgram/Phone/Keypad/MyPhoneKeypadProgram.vue';
import MyPhoneMenu from './PartsProgram/Phone/MyPhoneMenu.vue';
import MyPhoneRecentsProgram from './PartsProgram/Phone/Recents/MyPhoneRecentsProgram.vue';
import MyPhoneVoiceMailProgram from './PartsProgram/Phone/VoiceMail/MyPhoneVoiceMailProgram.vue';

export default {
  components: {MyPhoneKeypadProgram, MyPhoneRecentsProgram, MyPhoneVoiceMailProgram, MyPhoneMenu},
  data() {
    return {
      currentMenu: 'KeyPad'
    }
  },
  methods: {
    updateCurrentMenu(current){
      this.currentMenu = current
    }
  },
}
</script>

<style scoped>
.phone__programs {
  width: 335px;
  height: 705px;
  padding: 50px 10px 15px;
}
.phone__programs-menu {
  position: absolute;
  left: 0;
  right: 0;
  bottom: 20px;
}

</style>