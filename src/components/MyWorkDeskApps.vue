<template>
    <div>
      <div class="work__desk-apps">
        <div class="work__desp-widgets">
          <MyWeatherWidgets class="work__desp-widget"/>
          <MyCalendarWidgets class="work__desp-widget"/>
        </div>

        <MyFaceTimeIcon class="work__desk-app"/>

        <MyCalculatorIcon class="work__desk-app"/>

        <MySettingsIcon class="work__desk-app"/>

        <MyMapIcon class="work__desk-app"/>

        <MyAppStoreIcon class="work__desk-app"/>

        <MyCalendarIcon class="work__desk-app"/>

        <MyMailIcon class="work__desk-app"/>

        <MyCameraIcon class="work__desk-app"/>

        <MyGalleryIcon class="work__desk-app"/>

        
        <MyBookIcon class="work__desk-app"/>

        <MyActiveIcon class="work__desk-app"/>

        <!-- <MyCameraIcon class="work__desk-app"/> -->

        <MyContactsIcon class="work__desk-app"/>

        <MyChatsIcon class="work__desk-app"/>

        <MySiriIcon class="work__desk-app"/>
        
        <MyRulesIcon class="work__desk-app"/>

        <MyYouTubeIcon class="work__desk-app"/>

      </div>
      <div class="work__desk-bottom">
        <MyPhoneIcon class="work__desk-app"/>

        <MySafariIcon class="work__desk-app"/>

        <MyMessageIcon class="work__desk-app"/>

        <MyMusicIcon class="work__desk-app"/>

      </div>
    </div>
</template>


<script>
import MyActiveIcon from './Apps/Icons/MyActiveIcon.vue';
import MyAppStoreIcon from './Apps/Icons/MyAppStoreIcon.vue';
import MyBookIcon from './Apps/Icons/MyPinPong.vue';
import MyCalculatorIcon from './Apps/Icons/MyCalculatorIcon.vue';
import MyCalendarIcon from './Apps/Icons/MyCalendarIcon.vue';
import MyCameraIcon from './Apps/Icons/MyCameraIcon.vue';
import MyChatsIcon from './Apps/Icons/MyChatsIcon.vue';
import MyContactsIcon from './Apps/Icons/MyContactsIcon.vue';
import MyFaceTimeIcon from './Apps/Icons/MyFaceTimeIcon.vue';
import MyGalleryIcon from './Apps/Icons/MyGalleryIcon.vue';
import MyMailIcon from './Apps/Icons/MyMailIcon.vue';
import MyMapIcon from './Apps/Icons/MyMapIcon.vue';
import MyMessageIcon from './Apps/Icons/MyMessageIcon.vue';
import MyMusicIcon from './Apps/Icons/MyMusicIcon.vue';
import MyPhoneIcon from './Apps/Icons/MyPhoneIcon.vue';
import MyRulesIcon from './Apps/Icons/MyRulesIcon.vue';
import MySafariIcon from './Apps/Icons/MySafariIcon.vue';
import MySettingsIcon from './Apps/Icons/MySettingsIcon.vue';
import MySiriIcon from './Apps/Icons/MySiriIcon.vue';
import MyYouTubeIcon from './Apps/Icons/MyYouTubeIcon.vue';
import MyCalendarWidgets from './Apps/Widgets/MyCalendarWidgets.vue';
import MyWeatherWidgets from './Apps/Widgets/MyWeatherWidgets.vue';

export default {
  components: { MyFaceTimeIcon, MyCalculatorIcon, MySettingsIcon, MyAppStoreIcon, MyCalendarIcon, MyMailIcon, MyGalleryIcon, MyBookIcon, MyActiveIcon, MyContactsIcon, MyChatsIcon, MySiriIcon, MyRulesIcon, MyYouTubeIcon, MyPhoneIcon, MySafariIcon, MyMessageIcon, MyMusicIcon, MyCameraIcon, MyMapIcon, MyWeatherWidgets, MyCalendarWidgets },
}
</script>

<style scoped>
.work__desk-apps {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 15px;
}

.work__desp-widgets {
  grid-column: span 4;
  display: grid;
  gap: 28px;
  padding: 0 8px;
  margin-top: -85px;
  grid-template-columns: repeat(2, 1fr);
}

.work__desp-widget {
  background-color: lightblue;
  height: 130px;
  width: 130px;
  border-radius: 15px;
  padding: 12px;
  cursor: pointer;
}

.work__desk-bottom {
  background-color: rgba(000, 000, 000, 0.3);
  border-radius: 15px;
  /* padding: 5px; */
  display: flex;
  gap: 10px;
  position: absolute;
  bottom: 30px;
  left: 0;
  right: 0;
  margin: 0 auto;
  width: 290px;
}

.work__desk-app {
  cursor: pointer;
  display: flex;
  justify-content: center;
  align-items: center
}
</style>