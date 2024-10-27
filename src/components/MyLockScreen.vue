<template>
  <div class="lock__screen">
    <div class="lock__screen-top">
      <div class="lock__top-content">
        <div class="lock__screen-status">
          <p class="lock__screen-operator">Kovalcell</p>
          <MyStatusPhone/>
        </div>
        <div class="lock__screen-info">
          <p class="lock__info-text">
            {{ formattedDate }}
          </p>
          <p class="lock__info-time">
            {{ currentTime }}
          </p>
        </div>
      </div>

    </div>
    <div class="lock__screen-bottom">
      <div class="lock__bottom-tools">
        <svg class="lock__bottom-tool" height="25px" width="25px" version="1.1" id="Capa_1"
          xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 416.189 416.189"
          xml:space="preserve">
          <g>
            <g>
              <circle style="fill:#fff;" cx="208.095" cy="175.277" r="11.934" />
              <path style="fill:#fff;" d="M100.691,0v49.644l59.669,83.536v283.009h89.503V133.336l65.636-83.536V0
			C315.498,0,100.691,0,100.691,0z M208.095,199.144c-13.163,0-23.867-10.705-23.867-23.867s10.705-23.867,23.867-23.867
			c13.163,0,23.867,10.705,23.867,23.867S221.258,199.144,208.095,199.144z" />
            </g>
          </g>
        </svg>
        <svg class="lock__bottom-tool" width="25px" height="25px" viewBox="0 0 24 24" fill="none"
          xmlns="http://www.w3.org/2000/svg">
          <path fill-rule="evenodd" clip-rule="evenodd"
            d="M9.77778 21H14.2222C17.3433 21 18.9038 21 20.0248 20.2646C20.51 19.9462 20.9267 19.5371 21.251 19.0607C22 17.9601 22 16.4279 22 13.3636C22 10.2994 22 8.76721 21.251 7.6666C20.9267 7.19014 20.51 6.78104 20.0248 6.46268C19.3044 5.99013 18.4027 5.82123 17.022 5.76086C16.3631 5.76086 15.7959 5.27068 15.6667 4.63636C15.4728 3.68489 14.6219 3 13.6337 3H10.3663C9.37805 3 8.52715 3.68489 8.33333 4.63636C8.20412 5.27068 7.63685 5.76086 6.978 5.76086C5.59733 5.82123 4.69555 5.99013 3.97524 6.46268C3.48995 6.78104 3.07328 7.19014 2.74902 7.6666C2 8.76721 2 10.2994 2 13.3636C2 16.4279 2 17.9601 2.74902 19.0607C3.07328 19.5371 3.48995 19.9462 3.97524 20.2646C5.09624 21 6.65675 21 9.77778 21ZM12 9.27273C9.69881 9.27273 7.83333 11.1043 7.83333 13.3636C7.83333 15.623 9.69881 17.4545 12 17.4545C14.3012 17.4545 16.1667 15.623 16.1667 13.3636C16.1667 11.1043 14.3012 9.27273 12 9.27273ZM12 10.9091C10.6193 10.9091 9.5 12.008 9.5 13.3636C9.5 14.7192 10.6193 15.8182 12 15.8182C13.3807 15.8182 14.5 14.7192 14.5 13.3636C14.5 12.008 13.3807 10.9091 12 10.9091ZM16.7222 10.0909C16.7222 9.63904 17.0953 9.27273 17.5556 9.27273H18.6667C19.1269 9.27273 19.5 9.63904 19.5 10.0909C19.5 10.5428 19.1269 10.9091 18.6667 10.9091H17.5556C17.0953 10.9091 16.7222 10.5428 16.7222 10.0909Z"
            fill="#fff" />
        </svg>

      </div>
      <div class="lock__screen-line" @click="toggleUnlock"></div>
    </div>
  </div>
</template>

<script>
import MyStatusPhone from './MyStatusPhone.vue';

export default {
  components: { MyStatusPhone },
  data() {
    return {
      currentDate: new Date(), // Отримуємо поточну дату
    };
  },
  props: {
    toggleUnlock: {
      type: Function,
      required: true
    }
  },
  computed: {
    formattedDate() {
      const days = ['Неділя', 'Понеділок', 'Вівторок', 'Середа', 'Четвер', 'П’ятниця', 'Субота'];
      const months = ['січня', 'лютого', 'березня', 'квітня', 'травня', 'червня', 'липня', 'серпня', 'вересня', 'жовтня', 'листопада', 'грудня'];

      const dayName = days[this.currentDate.getDay()];
      const day = this.currentDate.getDate();
      const monthName = months[this.currentDate.getMonth()];

      return `${dayName}, ${day} ${monthName}`;
    },
    currentTime() {
      const hours = String(this.currentDate.getHours()).padStart(2, '0');
      const minutes = String(this.currentDate.getMinutes()).padStart(2, '0');

      return `${hours}:${minutes}`;
    }
  },
  mounted() {
    setInterval(() => {
      this.currentDate = new Date();
    }, 60000);
  }
}
</script>

<style scoped>
.lock__screen {
  width: 100%;
  height: 100%;
  padding: 12px 5px;
  color: #fff;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
}

.lock__screen-status {
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 0 15px;
  margin-bottom: 50px;
}

.lock__screen-info {
  text-align: center;
}

.lock__status-inner {
  display: flex;
  align-items: center;
  gap: 5px;
}

.lock__info-text {
  font-size: 23px;
}

.lock__info-time {
  font-size: 90px;
  font-weight: 500;
}

.lock__screen-bottom {
  display: flex;
  flex-direction: column;
  align-items: center;
  padding-bottom: 15px;
}

.lock__screen-line {
  width: 120px;
  height: 3px;
  background-color: #fff;
  border-radius: 5px;
  cursor: pointer;
}

.lock__bottom-tools {
  display: flex;
  justify-content: space-between;
  margin-bottom: 32px;
  width: 75%;
}

.lock__bottom-tool {
  background-color: rgba(000, 000, 000, 0.3);
  padding: 10px;
  border-radius: 50%;
}
</style>