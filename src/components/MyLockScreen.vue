<template>
  <div class="lock__screen">
    <div class="lock__screen-top">
      <div class="lock__top-content">
        <div class="lock__screen-status">
          <p class="lock__screen-operator">Kovalcell</p>
          <div class="lock__status-inner">
            <svg fill="#fff" width="15px" height="15px" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
              <path d="M18,2h4V22H18ZM10,7V22h4V7ZM6,12H2V22H6Z" />
            </svg>
            <svg width="15px" height="18px" viewBox="0 0 16 16" fill="none" xmlns="http://www.w3.org/2000/svg">
              <path
                d="M0 7L1.17157 5.82843C2.98259 4.01741 5.43884 3 8 3C10.5612 3 13.0174 4.01742 14.8284 5.82843L16 7L14.5858 8.41421L13.4142 7.24264C11.9783 5.8067 10.0307 5 8 5C5.96928 5 4.02173 5.8067 2.58579 7.24264L1.41421 8.41421L0 7Z"
                fill="#000" />
              <path
                d="M4.24264 11.2426L2.82843 9.82843L4 8.65685C5.06086 7.59599 6.49971 7 8 7C9.50029 7 10.9391 7.59599 12 8.65686L13.1716 9.82843L11.7574 11.2426L10.5858 10.0711C9.89999 9.38527 8.96986 9 8 9C7.03014 9 6.1 9.38527 5.41421 10.0711L4.24264 11.2426Z"
                fill="#fff" />
              <path
                d="M8 15L5.65685 12.6569L6.82842 11.4853C7.13914 11.1746 7.56057 11 8 11C8.43942 11 8.86085 11.1746 9.17157 11.4853L10.3431 12.6569L8 15Z"
                fill="#fff" />
            </svg>
            <svg fill="#ffffff" width="23px" height="23px" viewBox="0 0 56 56" xmlns="http://www.w3.org/2000/svg">
              <g id="SVGRepo_bgCarrier" stroke-width="0" />
              <g id="SVGRepo_tracerCarrier" stroke-linecap="round" stroke-linejoin="round" />
              <g id="SVGRepo_iconCarrier">
                <path
                  d="M 9.4633 42.0000 L 40.8481 42.0000 C 43.8786 42.0000 46.4304 41.7165 48.2379 39.9089 C 50.0457 38.1013 50.2935 35.5848 50.2935 32.5545 L 50.2935 23.4633 C 50.2935 20.4329 50.0457 17.8987 48.2379 16.1089 C 46.4127 14.3013 43.8786 14.0000 40.8481 14.0000 L 9.4101 14.0000 C 6.4329 14.0000 3.8810 14.3013 2.0734 16.1089 C .2658 17.9164 0 20.4329 0 23.4101 L 0 32.5545 C 0 35.5848 .2658 38.1190 2.0734 39.9089 C 3.8810 41.7165 6.4329 42.0000 9.4633 42.0000 Z M 8.9671 39.1468 C 7.1418 39.1468 5.2279 38.8987 4.1646 37.8355 C 3.0835 36.7544 2.8532 34.8759 2.8532 33.0506 L 2.8532 23.0202 C 2.8532 21.1595 3.0835 19.2456 4.1468 18.1823 C 5.2279 17.1013 7.1595 16.8532 9.0203 16.8532 L 41.3442 16.8532 C 43.1520 16.8532 45.0836 17.1190 46.1470 18.1823 C 47.2278 19.2633 47.4405 21.1418 47.4405 22.9671 L 47.4405 33.0506 C 47.4405 34.8759 47.2100 36.7544 46.1470 37.8355 C 45.0836 38.9165 43.1520 39.1468 41.3442 39.1468 Z M 52.7216 32.4835 C 54.1214 32.3949 56 30.6051 56 27.8937 C 56 25.2000 54.1214 23.4101 52.7216 23.3215 Z" />
              </g>

              <!-- Добавляем текстовое поле с цифрами -->
              <text x="25" y="30" font-size="25" fill="white" text-anchor="middle" alignment-baseline="middle">30</text>
            </svg>
          </div>
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
      <div class="lock__screen-line"></div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      currentDate: new Date(), // Отримуємо поточну дату
    };
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
  padding: 10px 5px;
  color: #fff;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
}

.lock__screen-top {
  padding-top: 17px;
}

.lock__screen-status {
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 0 15px;
  margin-bottom: 50px;
}

.lock__screen-operator {}

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
}

.lock__bottom-tools {
  display: flex;
  justify-content: space-between;
  margin-bottom: 32px;
  width: 75%;
  padding: 0 50px;
}

.lock__bottom-tool {
  background-color: rgba(000, 000, 000, 0.3);
  padding: 10px;
  border-radius: 50%;
}
</style>