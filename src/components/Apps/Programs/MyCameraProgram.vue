<template>
  <div class="camera_program">
    <video class="camera_program-video" ref="video" width="330" height="480" autoplay />
    <div class="camera_program-interface">
      <div class="camera_interface-top">
        <div class="camera_interface-top--left">
          <div class="camera_interface-left--content">
            <svg fill="#fff" width="18px" height="18px" viewBox="0 0 24 24" id="lightning" data-name="Flat Color"
              xmlns="http://www.w3.org/2000/svg" class="camera_interface-left--svg icon flat-color">
              <path id="primary"
                d="M18,11.74a1,1,0,0,0-.52-.63L14.09,9.43,15,3.14a1,1,0,0,0-1.78-.75l-7,9a1,1,0,0,0-.18.87,1.05,1.05,0,0,0,.6.67l4.27,1.71L10,20.86a1,1,0,0,0,.63,1.07A.92.92,0,0,0,11,22a1,1,0,0,0,.83-.45l6-9A1,1,0,0,0,18,11.74Z"
                style="fill: rgb(255, 255, 255);"></path>
            </svg>
          </div>
          <div class="camera_interface-left--content">
            <svg class="camera_interface-left--svg" fill="#fff" height="12px" width="12px" version="1.1" id="Layer_1"
              xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 512 512"
              xml:space="preserve">
              <g>
                <g>
                  <path
                    d="M506.298,202.547c-3.639-17.048-27.89-17.747-32.446-0.868c-15.349,56.82-67.255,98.886-128.808,98.843
        c-73.591-0.013-133.552-59.854-133.565-133.565c-0.042-61.556,42.024-113.458,98.84-128.808
        c16.83-4.546,16.229-28.799-0.869-32.446C292.244,2.03,274.371-0.001,256,0C114.796,0.031,0.031,114.79,0,256
        c0.031,141.21,114.796,255.969,256,256c141.204-0.031,255.969-114.79,256-256C512.001,237.628,509.971,219.756,506.298,202.547z" />
                </g>
              </g>
            </svg>
          </div>
        </div>
        <div class="camera_interface-center--content">
          <svg class="camera_interface-top--svg" width="16px" height="16px" viewBox="0 -4.5 20 20" version="1.1"
            xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink">
            <g id="Page-1" stroke="none" stroke-width="1" fill="none" fill-rule="evenodd">
              <g id="Dribbble-Light-Preview" transform="translate(-140.000000, -6683.000000)" fill="#fff">
                <g id="icons" transform="translate(56.000000, 160.000000)">
                  <path
                    d="M84,6532.61035 L85.4053672,6534 L94.0131154,6525.73862 L94.9311945,6526.61986 L94.9261501,6526.61502 L102.573446,6533.95545 L104,6532.58614 C101.8864,6530.55736 95.9854722,6524.89321 94.0131154,6523 C92.5472155,6524.40611 93.9757869,6523.03486 84,6532.61035"
                    id="arrow_up-[#340]">

                  </path>
                </g>
              </g>
            </g>
          </svg>
        </div>
        <svg width="20px" height="20px" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
          <path
            d="M18 16.3741C16.1233 16.7794 14.1038 17 12 17C9.89619 17 7.87667 16.7794 6 16.3741M16 20.667C14.7104 20.8852 13.3722 21 12 21C10.6278 21 9.28964 20.8852 8 20.667M19 12.0635C16.9408 12.6591 14.55 13 12 13C9.44999 13 7.05921 12.6591 5 12.0635M21 6C21 7.65685 16.9706 9 12 9C7.02944 9 3 7.65685 3 6C3 4.34315 7.02944 3 12 3C16.9706 3 21 4.34315 21 6Z"
            stroke="#fff" stroke-width="2" stroke-linecap="round" />
        </svg>
      </div>
      <div class="camera_interface-bottom">
        <ul class="camera_interface-funcrions">
          <li class="camera_interface-function">Пагрограф</li>
          <li class="camera_interface-function">Відео</li>
          <li class="camera_interface-function camera_interface-function--active">Фото</li>
          <li class="camera_interface-function">Портрет</li>
          <li class="camera_interface-function">Панорама</li>
        </ul>
        <div class="camera_interface-control">
          <div class="camera_interface-control-btn"></div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      stream: null,
    };
  },
  mounted() {
    this.startCamera(); // Запускаємо камеру при монтуванні компонента
  },
  beforeDestroy() {
    this.stopCamera(); // Останавливаем камеру при уничтожении компонента
  },
  methods: {
    async startCamera() {
      try {
        const stream = await navigator.mediaDevices.getUserMedia({ video: true });
        this.$refs.video.srcObject = stream;
        this.stream = stream; // Сохраняем поток, чтобы остановить его позже
      } catch (error) {
        console.error("Ошибка доступа к камере:", error);
      }
    },
    stopCamera() {
      if (this.stream) {
        this.stream.getTracks().forEach(track => track.stop());
      }
    }
  }
}
</script>

<style scoped>
.camera_program-video {
  width: 335px;
  height: 705px;
  border-radius: 50px;
  object-fit: cover;
  margin-top: 5px;
}

.camera_program-interface {
  position: absolute;
  display: flex;
  justify-content: space-between;
  flex-direction: column;
  top: -7px;
  bottom: -7px;
  align-items: center;
  align-content: center;
  left: 0;
  right: 0;
}

.camera_interface-top {
  display: flex;
  justify-content: space-between;
  align-items: center;
  height: 100px;
  width: 340px;
  border-radius: 50px;
  border-bottom-left-radius: 0;
  border-bottom-right-radius: 0;
  padding: 0 15px;
  padding-top: 35px;
  gap: 10px;
  background-color: rgba(000, 000, 000, 0.8);
}

.camera_interface-top--svg {}

.camera_interface-left--content {
  width: 24px;
  height: 24px;
  border-radius: 50%;
  border: 1px solid;
  display: flex;
  justify-content: center;
  align-items: center
}

.camera_interface-top--left {
  align-items: center;
  display: flex;
  gap: 10px;
}

.camera_interface-center--content {
  background-color: rgba(255, 255, 255, 0.2);
  border-radius: 50%;
  width: 24px;
  height: 24px;
  display: flex;
  justify-content: center;
  align-items: center;
  transform: translateX(-50%);
}

.camera_interface-bottom {
  padding: 15px 5px 3px;
  height: 100px;
  width: 334px;
  border-radius: 50px;
  border-top-left-radius: 0;
  border-top-right-radius: 0;
  background-color: rgba(000, 000, 000, 0.8);
}

.camera_interface-funcrions {
  display: flex;
  justify-content: space-between;
  list-style: none;
  text-align: center;
  margin-bottom: 5px;
}

.camera_interface-function {
  text-transform: uppercase;
  font-size: 12px;
}

.camera_interface-function--active {
  color: #dacd3a;
}

.camera_interface-control {
  display: flex;
  justify-content: center;
}

.camera_interface-control-btn {
  width: 49px;
  height: 49px;
  background-color: #fff;
  border-radius: 50%;
}
</style>
