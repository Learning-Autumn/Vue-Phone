<template>
  <li class="oclock__program-item">
    <div class="oclock__program-item-left">
      <p class="oclock__program-item-time">
        {{ String(Time.minutes).padStart(2, '0') }}:{{ String(Time.seconds).padStart(2, '0') }}
      </p>
    </div>
    <div class="oclock__program-item-right">
      <button @click="startTimer" class="oclock__program-item-button">
        <svg width="20px" viewBox="0 0 16 16" xmlns="http://www.w3.org/2000/svg" fill="#000000"><g id="SVGRepo_bgCarrier" stroke-width="0"></g><g id="SVGRepo_tracerCarrier" stroke-linecap="round" stroke-linejoin="round"></g><g id="SVGRepo_iconCarrier"> <path d="m 2 2.5 v 11 c 0 1.5 1.269531 1.492188 1.269531 1.492188 h 0.128907 c 0.246093 0.003906 0.488281 -0.050782 0.699218 -0.171876 l 9.796875 -5.597656 c 0.433594 -0.242187 0.65625 -0.734375 0.65625 -1.226562 c 0 -0.492188 -0.222656 -0.984375 -0.65625 -1.222656 l -9.796875 -5.597657 c -0.210937 -0.121093 -0.453125 -0.175781 -0.699218 -0.175781 h -0.128907 s -1.269531 0 -1.269531 1.5 z m 0 0" fill="#33d052"></path> </g></svg>
      </button>
    </div>
  </li>
</template>

<script>
  export default {
    data() {
      return {
      }
    },
    props: {
      Time: {
        type: Object,
        required: true,
      },
      isActive: {
        type: Boolean,
        require: true,
      }
    },
    methods: {
      startTimer(){
        if (JSON.stringify(this.Time) !== '{"minutes":0,"seconds":0}'){
          this.$emit('startTimer', this.Time)
        }
        
      }
    },
  }
</script>

<style scoped>
.oclock__program-item {
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding-right: 8px;
  margin-bottom: 10px;
}
.oclock__program-item-time {
  color: #adadaf;
  font-size: 50px;
  font-weight: 300;
}
.oclock__program-item-button {
  background-color: #092911;
  border: none;
  width: 50px;
  height: 50px;
  border-radius: 50%;
}
.oclock__program-item-button svg{
}
</style>