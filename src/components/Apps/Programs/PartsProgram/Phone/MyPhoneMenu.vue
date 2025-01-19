<template>
  <div class="phone__program-inner">
    <ul class="phone__program-list">
      <li
        :class="{
          'phone__program-item': true,
          'phone__program-item--active': isOpenMenu === 'Recents',
        }"
      >
        <svg
          @click="toggleMenu('Recents')"
          width="24px"
          viewBox="0 0 19 19"
          xmlns="http://www.w3.org/2000/svg"
          fill="#5c5c5f"
          class="phone__program-svg"
        >
          <g id="SVGRepo_bgCarrier" stroke-width="0"></g>
          <g
            id="SVGRepo_tracerCarrier"
            stroke-linecap="round"
            stroke-linejoin="round"
          ></g>
          <g id="SVGRepo_iconCarrier">
            <path
              fill="#5c5c5f"
              fill-rule="evenodd"
              d="M207.960546,159.843246 L210.399107,161.251151 C210.637153,161.388586 210.71416,161.70086 210.580127,161.933013 C210.442056,162.172159 210.144067,162.258604 209.899107,162.117176 L207.419233,160.68542 C207.165323,160.8826 206.846372,161 206.5,161 C205.671573,161 205,160.328427 205,159.5 C205,158.846891 205.417404,158.291271 206,158.085353 L206,153.503423 C206,153.22539 206.231934,153 206.5,153 C206.776142,153 207,153.232903 207,153.503423 L207,158.085353 C207.582596,158.291271 208,158.846891 208,159.5 C208,159.6181 207.986351,159.733013 207.960546,159.843246 Z M206.5,169 C211.746705,169 216,164.746705 216,159.5 C216,154.253295 211.746705,150 206.5,150 C201.253295,150 197,154.253295 197,159.5 C197,164.746705 201.253295,169 206.5,169 Z"
              transform="translate(-197 -150)"
            ></path>
          </g>
        </svg>
        <p class="phone__program-text">Recents</p>
      </li>
      <li
        :class="{
          'phone__program-item': true,
          'phone__program-item--active': isOpenMenu === 'KeyPad',
        }"
        style="margin-right: -10px"
      >
        <svg
          @click="toggleMenu('KeyPad')"
          width="24px"
          fill="#5c5c5f"
          viewBox="0 0 52 52"
          data-name="Layer 1"
          xmlns="http://www.w3.org/2000/svg"
          class="phone__program-svg"
        >
          <g id="SVGRepo_bgCarrier" stroke-width="0"></g>
          <g
            id="SVGRepo_tracerCarrier"
            stroke-linecap="round"
            stroke-linejoin="round"
          ></g>
          <g id="SVGRepo_iconCarrier">
            <path
              d="M8.55,36.91A6.55,6.55,0,1,1,2,43.45,6.54,6.54,0,0,1,8.55,36.91Zm17.45,0a6.55,6.55,0,1,1-6.55,6.54A6.55,6.55,0,0,1,26,36.91Zm17.45,0a6.55,6.55,0,1,1-6.54,6.54A6.54,6.54,0,0,1,43.45,36.91ZM8.55,19.45A6.55,6.55,0,1,1,2,26,6.55,6.55,0,0,1,8.55,19.45Zm17.45,0A6.55,6.55,0,1,1,19.45,26,6.56,6.56,0,0,1,26,19.45Zm17.45,0A6.55,6.55,0,1,1,36.91,26,6.55,6.55,0,0,1,43.45,19.45ZM8.55,2A6.55,6.55,0,1,1,2,8.55,6.54,6.54,0,0,1,8.55,2ZM26,2a6.55,6.55,0,1,1-6.55,6.55A6.55,6.55,0,0,1,26,2ZM43.45,2a6.55,6.55,0,1,1-6.54,6.55A6.55,6.55,0,0,1,43.45,2Z"
              fill-rule="evenodd"
            ></path>
          </g>
        </svg>
        <p class="phone__program-text">KeyPad</p>
      </li>
      <li
        :class="{
          'phone__program-item': true,
          'phone__program-item--active': isOpenMenu === 'VoiceMail',
        }"
      >
        <svg
          @click="toggleMenu('VoiceMail')"
          width="40px"
          fill="#5c5c5f"
          viewBox="0 0 24 24"
          xmlns="http://www.w3.org/2000/svg"
          class="phone__program-svg"
          style="margin-top: -10px"
        >
          <g id="SVGRepo_bgCarrier" stroke-width="0"></g>
          <g
            id="SVGRepo_tracerCarrier"
            stroke-linecap="round"
            stroke-linejoin="round"
          ></g>
          <g id="SVGRepo_iconCarrier">
            <g id="Voicemail">
              <path
                d="M17.435,7.5a4.5,4.5,0,0,0-2.82,8H9.385a4.494,4.494,0,1,0-2.82,1h10.87a4.5,4.5,0,0,0,0-9ZM3.065,12a3.5,3.5,0,1,1,3.56,3.5h-.06A3.5,3.5,0,0,1,3.065,12Zm14.37,3.5h-.06a3.53,3.53,0,1,1,.06,0Z"
              ></path>
            </g>
          </g>
        </svg>
        <p class="phone__program-text" style="margin-top: -5px">VoiceMail</p>
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
    },
  },
  methods: {
    toggleMenu(current) {
      this.$emit("changeMenu", current);
    },
  },
};
</script>

<style scoped>
.phone__program-list {
  list-style: none;
  display: flex;
  justify-content: space-around;
  align-items: center;
}
.phone__program-item {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 5px;
}
.phone__program-text {
  font-size: 12px;
  color: #5c5c5f;
}
.phone__program-item--active .phone__program-text {
  color: #0a84fe;
}

.phone__program-item--active svg {
  fill: #0a84fe;
}
.phone__program-item--active path {
  fill: #0a84fe;
}

.phone__program-svg {
  cursor: pointer;
}
</style>
