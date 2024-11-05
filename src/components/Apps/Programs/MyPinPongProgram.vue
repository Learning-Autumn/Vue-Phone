<template>
  <div class="pin-pong__program" @mousemove="updateCursorPosition" ref="programContainer">
    <!-- <div>
      <p>Позиція курсора:</p>
      <p>X: {{ cursorX }}, Y: {{ cursorY }}</p>
    </div> -->
    <svg v-if="isGameOver" class="pin-pong__info" fill="#fff" height="64px" width="64px" version="1.1" id="Layer_1"
      xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 290.477 290.477"
      xml:space="preserve" stroke="#fff">

      <g id="SVGRepo_bgCarrier" stroke-width="0" />

      <g id="SVGRepo_tracerCarrier" stroke-linecap="round" stroke-linejoin="round" />

      <g id="SVGRepo_iconCarrier">
        <g>
          <g>
            <g>
              <polygon
                points="66.667,109.524 28.571,109.524 28.571,119.048 19.048,119.048 19.048,185.714 28.571,185.714 28.571,195.238 66.667,195.238 66.667,185.714 76.191,185.714 76.191,147.619 47.62,147.619 47.62,157.143 66.667,157.143 66.667,176.19 57.144,176.19 57.144,185.714 38.096,185.714 38.096,176.19 28.571,176.19 28.571,128.571 38.096,128.571 38.096,119.048 57.144,119.048 57.144,128.571 76.191,128.571 76.191,119.048 66.667,119.048 " />
              <path
                d="M138.096,119.048h-4.762v-9.524H95.238v9.524h-4.762v9.524h-4.762v66.667h9.524v-28.571h38.095v28.571h9.524v-66.667 h-4.762V119.048z M133.334,157.143H95.238v-19.048h4.762v-9.524h4.762v-9.524h19.048v9.524h4.762v9.524h4.762V157.143z" />
              <polygon
                points="178.571,142.271 170.386,109.524 152.381,109.524 152.381,195.238 161.906,195.238 161.906,119.048 162.949,119.048 172.472,157.143 184.672,157.143 194.196,119.048 195.239,119.048 195.239,195.238 204.763,195.238 204.763,109.524 186.758,109.524 " />
              <polygon
                points="266.667,119.048 266.667,109.524 214.287,109.524 214.287,195.238 266.667,195.238 266.667,185.714 223.811,185.714 223.811,157.143 261.906,157.143 261.906,147.619 223.811,147.619 223.811,119.048 " />
              <path
                d="M66.667,204.762H28.571v9.524h-9.524v66.667h9.524v9.524h38.095v-9.524h9.524v-66.667h-9.524V204.762z M66.667,223.81 v47.619h-9.524v9.524H38.096v-9.524h-9.524V223.81h9.524v-9.524h19.048v9.524H66.667z" />
              <polygon
                points="133.334,261.905 128.571,261.905 128.571,271.429 123.811,271.429 123.811,280.952 104.763,280.952 104.763,271.429 100.001,271.429 100.001,261.905 95.238,261.905 95.238,204.762 85.714,204.762 85.714,271.429 90.477,271.429 90.477,280.952 95.238,280.952 95.238,290.476 133.334,290.476 133.334,280.952 138.096,280.952 138.096,271.429 142.857,271.429 142.857,204.762 133.334,204.762 " />
              <polygon
                points="152.381,290.476 204.763,290.476 204.763,280.952 161.906,280.952 161.906,252.381 200.001,252.381 200.001,242.857 161.906,242.857 161.906,214.286 204.763,214.286 204.763,204.762 152.381,204.762 " />
              <path
                d="M261.906,247.619h9.524v-33.333h-9.524v-9.524h-47.619v85.714h9.524v-32.062l38.095,29.629v2.433h9.524v-7.09 l-33.743-26.243h24.219V247.619z M252.381,247.619h-28.552l-0.019,4.757v-38.09h28.571v9.524h9.524v14.286h-9.524V247.619z" />
              <path
                d="M195.239,104.762h19.048v-9.524h-19.048V28.571C195.239,12.814,182.425,0,166.667,0h-47.619 C103.29,0,90.477,12.814,90.477,28.571v66.667H71.43v9.524h19.048H195.239z M100.001,28.571c0-10.505,8.543-19.048,19.048-19.048 h47.619c10.505,0,19.048,8.543,19.048,19.048v66.667h-85.715V28.571z" />
              <polygon
                points="147.62,19.048 138.096,19.048 138.096,28.571 114.287,28.571 114.287,38.095 138.096,38.095 138.096,76.19 147.62,76.19 147.62,38.095 171.43,38.095 171.43,28.571 147.62,28.571 " />
            </g>
          </g>
        </g>
      </g>
    </svg>
    <div class="pin-pong__ball" :style="{ left: positionBallX + 'px', top: positionBallY + 'px' }"></div>
    <div class="pin-pong__platform" :style="{ left: cursorX + 'px' }"></div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      cursorX: 0,
      cursorY: 0,
      containerOffsetX: 0,
      containerOffsetY: 0,
      containerWidth: 0,
      containerHeight: 0,
      positionBallX: 0,
      positionBallY: 0,
      ballSpeedX: 2,
      ballSpeedY: 2,
      ballDiameter: 20,
      platformWidth: 50,
      platformHeight: 2,
      gameLoop: null,
      isGameOver: false,
    };
  },
  mounted() {
    this.setContainerOffset();
    this.startBallMovement();
  },
  beforeDestroy() {
    cancelAnimationFrame(this.gameLoop);
  },
  methods: {
    setContainerOffset() {
      const rect = this.$refs.programContainer.getBoundingClientRect();
      this.containerOffsetX = rect.left;
      this.containerOffsetY = rect.top;
      this.containerWidth = rect.width;
      this.containerHeight = rect.height;
    },
    updateCursorPosition(event) {
      const rawX = event.clientX - this.containerOffsetX - this.platformWidth / 2;
      this.cursorX = Math.max(0, Math.min(rawX, this.containerWidth - this.platformWidth));
    },
    startBallMovement() {
      const moveBall = () => {
        this.positionBallX += this.ballSpeedX;
        this.positionBallY += this.ballSpeedY;

   
        if (this.positionBallX <= 0 || this.positionBallX + this.ballDiameter >= this.containerWidth) {
          this.ballSpeedX *= -1; 
        }
        if (this.positionBallY <= 0) {
          this.ballSpeedY *= -1; 
        }

        const platformTop = this.containerHeight - 50 - this.platformHeight;
        const platformLeft = this.cursorX;
        const platformRight = this.cursorX + this.platformWidth;

        if (
          this.positionBallY + this.ballDiameter >= platformTop &&
          this.positionBallX + this.ballDiameter / 2 >= platformLeft &&
          this.positionBallX + this.ballDiameter / 2 <= platformRight
        ) {
          this.ballSpeedY *= -1;
        }
        if (this.positionBallY + this.ballDiameter >= this.containerHeight) {
          this.endGame(); 
        } else {
          this.gameLoop = requestAnimationFrame(moveBall); 
        }
      };

      this.gameLoop = requestAnimationFrame(moveBall);
    },
    endGame() {
      this.isGameOver = true;
      cancelAnimationFrame(this.gameLoop);
      setTimeout(this.resetBall, 5000); 
    },
    resetBall() {
      this.positionBallX = this.containerWidth / 2 - this.ballDiameter / 2;
      this.positionBallY = 0;
      this.ballSpeedX = Math.random() > 0.5 ? 2 : -2;
      this.ballSpeedY = 2;
      this.startBallMovement();
      this.isGameOver = false;
    },
  }
};
</script>

<style scoped>
.pin-pong__program {
  width: 335px;
  height: 705px;
  /* border: 1px solid #fff; */
  position: relative;
  /* border-radius: 50px; */
}

.pin-pong__platform {
  position: absolute;
  bottom: 50px;
  width: 50px;
  background-color: #fff;
  height: 2px;
}

.pin-pong__ball {
  position: absolute;
  width: 20px;
  height: 20px;
  background-color: #fff;
  border-radius: 50%;
}

.pin-pong__info {
  position: absolute;
  top: 50%;
  transform: translateY(-50%);
  left: 0;
  right: 0;
  margin: 0 auto;
  text-align: center
}
</style>
