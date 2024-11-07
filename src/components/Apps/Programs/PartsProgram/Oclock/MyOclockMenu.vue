<template>
  <div class="oclock__program-inner">
    <ul class="oclock__program-list">
      <li @click="changeMenu('WorldClock')" :class="{ 'oclock__program-item': true, 'oclock__program-item--active': isOpenMenu === 'WorldClock' }">
        <svg class="oclock__program-svg" version="1.1" id="Layer_1"
          xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" width="24px" height="24px"
          viewBox="0 0 64 64" enable-background="new 0 0 64 64" xml:space="preserve" fill="#848484" stroke="#848484">
          <g id="SVGRepo_bgCarrier" stroke-width="0"></g>
          <g id="SVGRepo_tracerCarrier" stroke-linecap="round" stroke-linejoin="round"></g>
          <g id="SVGRepo_iconCarrier">
            <path fill="none" stroke="#848484" stroke-width="2" stroke-miterlimit="10"
              d="M32.001,0.887c17.184,0,31.113,13.929,31.112,31.113 C63.114,49.185,49.184,63.115,32,63.113C14.815,63.114,0.887,49.185,0.888,32.001C0.885,14.816,14.815,0.887,32.001,0.887z">
            </path>
            <line fill="none" stroke="#848484" stroke-width="2" stroke-miterlimit="10" x1="32" y1="1" x2="32" y2="63">
            </line>
            <line fill="none" stroke="#848484" stroke-width="2" stroke-miterlimit="10" x1="63" y1="32" x2="1" y2="32">
            </line>
            <path fill="none" stroke="#848484" stroke-width="2" stroke-miterlimit="10"
              d="M30,1c0,0-14,11-14,31s14,31,14,31"></path>
            <path fill="none" stroke="#848484" stroke-width="2" stroke-miterlimit="10"
              d="M34,1c0,0,14,11,14,31S34,63,34,63"></path>
            <path fill="none" stroke="#848484" stroke-width="2" stroke-miterlimit="10"
              d="M8,12c0,0,5,10,24,10s24-10,24-10"></path>
            <path fill="none" stroke="#848484" stroke-width="2" stroke-miterlimit="10"
              d="M8,52c0,0,5-10,24-10s24,10,24,10"></path>
          </g>
        </svg>
        <p class="oclock__program-text">
          World Clock
        </p>
      </li>
      <li @click="changeMenu('Alarms')" :class="{ 'oclock__program-item': true, 'oclock__program-item--active': isOpenMenu === 'Alarms' }">
        <svg class="oclock__program-svg icon" width="24px" height="24px"
          viewBox="0 0 1024 1024" fill="#848484" version="1.1" xmlns="http://www.w3.org/2000/svg" stroke="#848484">
          <g id="SVGRepo_bgCarrier" stroke-width="0"></g>
          <g id="SVGRepo_tracerCarrier" stroke-linecap="round" stroke-linejoin="round"></g>
          <g id="SVGRepo_iconCarrier">
            <path
              d="M176.8 983.2c-4.8 0-9.6-1.6-13.6-5.6-8.8-7.2-9.6-20.8-2.4-30.4l80-93.6-4.8-4C135.2 768.8 77.6 648 77.6 519.2c0-49.6 8.8-98.4 24.8-144.8l1.6-4-3.2-2.4C62.4 338.4 40 293.6 40 245.6c0-84.8 68.8-153.6 153.6-153.6 42.4 0 81.6 16.8 110.4 46.4l3.2 3.2 4-1.6c60-31.2 127.2-47.2 195.2-47.2 68.8 0 138.4 17.6 200.8 50.4l4 2.4 3.2-3.2c28.8-31.2 69.6-49.6 112.8-49.6 84.8 0 153.6 68.8 153.6 153.6 0 51.2-25.6 99.2-68 128l-4 2.4 1.6 4c15.2 44.8 23.2 91.2 23.2 140 0 129.6-57.6 250.4-158.4 331.2l-4.8 3.2 78.4 93.6c4 4 5.6 9.6 4.8 15.2-0.8 5.6-3.2 11.2-8 15.2-4 3.2-8.8 4.8-14.4 4.8-6.4 0-12-2.4-16.8-7.2l-81.6-96-4 2.4c-68 41.6-145.6 64-224.8 64-80 0-157.6-22.4-224.8-64l-4-2.4-82.4 96.8c-4 2.4-10.4 5.6-16 5.6zM505.6 134.4c-212 0-384 172-384 384s172 384 384 384 384-172 384-384-172.8-384-384-384z m320 0c-27.2 0-52.8 9.6-72.8 28l-5.6 4.8 5.6 4c56.8 40.8 103.2 95.2 134.4 157.6l3.2 6.4 5.6-4.8c25.6-20.8 40-52 40-84.8 0-61.6-49.6-111.2-110.4-111.2z m-631.2 0c-60.8 0-110.4 49.6-110.4 110.4 0 30.4 12 58.4 33.6 79.2l5.6 5.6 3.2-6.4c32-61.6 79.2-116 136.8-155.2l6.4-4-5.6-4.8c-20-16-44.8-24.8-69.6-24.8z"
              fill=""></path>
            <path
              d="M504.8 540c-12 0-21.6-9.6-21.6-21.6V269.6c0-12 9.6-21.6 21.6-21.6s21.6 9.6 21.6 21.6v227.2h212c12 0 21.6 9.6 21.6 21.6 0 12-9.6 21.6-21.6 21.6H504.8z"
              fill=""></path>
          </g>
        </svg>
        <p class="oclock__program-text">
          Alarms
        </p>
      </li>
      <li @click="changeMenu('Stopwatch')" :class="{ 'oclock__program-item': true, 'oclock__program-item--active': isOpenMenu === 'Stopwatch' }">
        <svg class="oclock__program-svg" fill="#848484" width="24px" height="24px" viewBox="0 0 56 56" xmlns="http://www.w3.org/2000/svg"
          stroke="#848484">
          <g id="SVGRepo_bgCarrier" stroke-width="0"></g>
          <g id="SVGRepo_tracerCarrier" stroke-linecap="round" stroke-linejoin="round"></g>
          <g id="SVGRepo_iconCarrier">
            <path
              d="M 27.9999 54.2734 C 41.0546 54.2734 51.9063 43.4453 51.9063 30.3672 C 51.9063 24.9062 50.0079 19.8438 46.8436 15.7891 L 48.6716 13.9375 C 49.2107 13.3984 49.5155 12.6719 49.5155 12.0391 C 49.5155 10.7266 48.4609 9.6719 47.1014 9.6719 C 46.3046 9.6719 45.7421 9.9062 45.1796 10.4453 L 43.3983 12.2031 C 39.8124 9.1562 35.3593 7.1172 30.4843 6.6016 L 30.4843 4.3047 C 30.4843 2.8984 29.3593 1.7266 27.9765 1.7266 C 26.5936 1.7266 25.4452 2.8984 25.4452 4.3047 L 25.4452 6.6016 C 13.5390 7.8906 4.0937 18.1562 4.0937 30.3672 C 4.0937 43.4453 14.9218 54.2734 27.9999 54.2734 Z M 27.9999 50.2891 C 16.9374 50.2891 8.1014 41.4297 8.1014 30.3672 C 8.1014 19.3281 16.9140 10.4453 27.9765 10.4453 C 39.0155 10.4453 47.8983 19.3281 47.9219 30.3672 C 47.9454 41.4297 39.0390 50.2891 27.9999 50.2891 Z M 27.9999 34.1640 C 30.0858 34.1640 31.7499 32.4766 31.7499 30.3906 C 31.7499 28.9141 30.9062 27.625 29.6171 26.9922 L 29.6171 15.3438 C 29.6171 14.4297 28.8905 13.7266 27.9765 13.7266 C 27.0624 13.7266 26.3593 14.4297 26.3593 15.3438 L 26.3593 26.9687 C 25.0702 27.6484 24.2030 28.9141 24.2030 30.3906 C 24.2030 32.4766 25.8905 34.1640 27.9999 34.1640 Z">
            </path>
          </g>
        </svg>
        <p class="oclock__program-text">
          Stopwatch
        </p>
      </li>
      <li @click="changeMenu('Timers')" :class="{ 'oclock__program-item': true, 'oclock__program-item--active': isOpenMenu === 'Timers' }">
        <svg  class="oclock__program-svg" fill="#848484" version="1.1" id="Capa_1"
          xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" width="24px" height="24px"
          viewBox="0 0 441.553 441.553" xml:space="preserve" stroke="#848484">
          <g id="SVGRepo_bgCarrier" stroke-width="0"></g>
          <g id="SVGRepo_tracerCarrier" stroke-linecap="round" stroke-linejoin="round"></g>
          <g id="SVGRepo_iconCarrier">
            <g>
              <path
                d="M236.749,58.705V48.119c0-2.775,3.665-8.121,6.608-12.415c4.095-5.975,7.963-11.619,7.963-16.907 C251.32,8.432,241.516,0,229.463,0h-39.051c-12.053,0-21.857,8.432-21.857,18.797c0,5.288,3.868,10.932,7.963,16.907 c2.945,4.294,6.608,9.64,6.608,12.415v14.896c0,2.415,1.957,4.371,4.372,4.371c2.415,0,4.372-1.957,4.372-4.371V48.119 c0-5.484-3.954-11.252-8.14-17.358c-2.866-4.181-6.431-9.383-6.431-11.963c0-5.451,6.006-10.055,13.114-10.055h39.051 c7.109,0,13.114,4.604,13.114,10.055c0,2.581-3.565,7.783-6.433,11.963c-4.187,6.106-8.139,11.875-8.139,17.358v14.896 c0,2.415,1.957,4.371,4.372,4.371c0.007,0,0.014-0.001,0.022-0.001c0.029,0,0.058,0.009,0.089,0.009 c100.746,0,182.71,81.962,182.71,182.708c0,100.746-81.964,182.709-182.71,182.709c-83.231,0-158.321-55.611-176.85-136.643 c-0.575-2.514-2.731-3.588-4.938-3.199c-0.074,0.014-23.99,5.154-23.99,5.154l34.704-74.841c0.397-0.854,0.96-1.404,1.588-1.548 c0.626-0.152,1.374,0.107,2.102,0.705l65.517,53.889c0,0-28.299,6.84-28.323,6.846c-2.31,0.701-4.427,1.406-2.576,6.766 c20.453,59.229,71.912,100.229,133.583,100.229c77.629,0,140.786-63.156,140.786-140.785c0-37.256-15.19-71.939-42.772-97.665 c-27.059-25.237-62.88-39.135-100.867-39.135c-2.415,0-4.372,1.957-4.372,4.372c0,0.371,0.112,116.934,0.112,116.934 c0,12.053,9.804,21.857,21.857,21.857h81.962c2.415,0,4.371-1.957,4.371-4.371c0-2.416-1.956-4.371-4.371-4.371h-81.962 c-7.232,0-13.115-5.883-13.115-13.115V121.44c72.312,2.259,130.412,58.764,130.412,127.949 c0,72.809-59.234,132.041-132.043,132.041c-56.713,0-106.208-36.4-124.199-90.908l23.592-5.697 c3.899-0.939,6.543-3.256,7.253-6.352c0.71-3.098-0.659-6.332-3.756-8.879L70.656,215.69c-2.824-2.32-6.323-3.226-9.598-2.476 c-3.276,0.749-6.038,3.078-7.575,6.393l-34.718,74.872c-1.688,3.639-1.52,7.15,0.465,9.629c1.503,1.883,3.817,2.875,6.559,2.875 c0.873,0,1.787-0.102,2.733-0.307l19.795-4.27c23.254,82.133,98.364,139.146,184.171,139.146 c105.568,0,191.453-85.885,191.453-191.451C423.942,145.96,340.357,60.979,236.749,58.705z">
              </path>
            </g>
          </g>
        </svg>
        <p class="oclock__program-text">
          Timers
        </p>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  props: {
    isOpenMenu: {
      type: String,
      required: true,
    }
  },
  methods: {
    changeMenu(newMenu) {
      this.$emit('updateMenu', newMenu);
    }
  }
}
</script>

<style scoped>
.oclock__program-list {
  list-style: none;
  padding: 0 25px;
}

.oclock__program-list {
  display: flex;
  justify-content: space-between;
}

.oclock__program-item {
  display: flex;
  align-items: center;
  flex-direction: column;
  justify-items: center;
  cursor: pointer;
}

.oclock__program-item--active {
  color: #ff9f0a;
}

.oclock__program-item--active svg {
  fill: #ff9f0a;
}

.oclock__program-item--active path,
.oclock__program-item--active line {
  stroke: #ff9f0a;
}

.oclock__program-svg {
  margin-bottom: 10px;
}

.oclock__program-text {
  font-size: 12px;
}
</style>