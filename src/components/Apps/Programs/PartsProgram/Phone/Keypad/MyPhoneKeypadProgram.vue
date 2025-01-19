<template>
  <div class="keypad__program">
    <input class="keypad__program-input" type="" name="" value="" v-model="enteredText" />
    <svg
      v-if="enteredText.length > 0"
      @click="enteredTextClear"
      @dblclick="enteredTextDelete"
      class="keypad__program-clear"
      width="25px"
      viewBox="0 0 76 76"
      xmlns="http://www.w3.org/2000/svg"
      xmlns:xlink="http://www.w3.org/1999/xlink"
      version="1.1"
      baseProfile="full"
      enable-background="new 0 0 76.00 76.00"
      xml:space="preserve"
      fill="#000000"
    >
      <g id="SVGRepo_bgCarrier" stroke-width="0"></g>
      <g id="SVGRepo_tracerCarrier" stroke-linecap="round" stroke-linejoin="round"></g>
      <g id="SVGRepo_iconCarrier">
        <path
          fill="#5c5c5f"
          fill-opacity="1"
          stroke-width="0.2"
          stroke-linejoin="round"
          d="M 18.0147,41.5355C 16.0621,39.5829 16.0621,36.4171 18.0147,34.4645L 26.9646,25.5149C 28.0683,24.4113 29,24 31,24L 52,24C 54.7614,24 57,26.2386 57,29L 57,47C 57,49.7614 54.7614,52 52,52L 31,52C 29,52 28.0683,51.589 26.9646,50.4854L 18.0147,41.5355 Z M 47.5281,42.9497L 42.5784,37.9999L 47.5281,33.0502L 44.9497,30.4717L 40,35.4215L 35.0502,30.4717L 32.4718,33.0502L 37.4215,37.9999L 32.4718,42.9497L 35.0502,45.5281L 40,40.5783L 44.9497,45.5281L 47.5281,42.9497 Z "
        ></path>
      </g>
    </svg>
    <div class="keypad__program-keyboard">
      <div class="keypad__program-key">
        <div @click="tounchKey($event)" class="keypad__program-num">1</div>
      </div>
      <div class="keypad__program-key">
        <div @click="tounchKey($event)" class="keypad__program-num">2</div>
        <div class="keypad__program-desc">ABC</div>
      </div>
      <div class="keypad__program-key">
        <div @click="tounchKey($event)" class="keypad__program-num">3</div>
        <div class="keypad__program-desc">DEF</div>
      </div>
      <div class="keypad__program-key">
        <div @click="tounchKey($event)" class="keypad__program-num">4</div>
        <div class="keypad__program-desc">GHI</div>
      </div>
      <div class="keypad__program-key">
        <div @click="tounchKey($event)" class="keypad__program-num">5</div>
        <div class="keypad__program-desc">JKL</div>
      </div>
      <div class="keypad__program-key">
        <div @click="tounchKey($event)" class="keypad__program-num">6</div>
        <div class="keypad__program-desc">MNO</div>
      </div>
      <div class="keypad__program-key">
        <div @click="tounchKey($event)" class="keypad__program-num">7</div>
        <div class="keypad__program-desc">PQRS</div>
      </div>
      <div class="keypad__program-key">
        <div @click="tounchKey($event)" class="keypad__program-num">8</div>
        <div class="keypad__program-desc">TUV</div>
      </div>
      <div class="keypad__program-key">
        <div @click="tounchKey($event)" class="keypad__program-num">9</div>
        <div class="keypad__program-desc">WXYZ</div>
      </div>
      <div class="keypad__program-key">
        <div @click="tounchKey($event)" class="keypad__program-num">*</div>
        <div class="keypad__program-desc"></div>
      </div>
      <div class="keypad__program-key">
        <div @click="tounchKey($event)" class="keypad__program-num">0</div>
        <div class="keypad__program-desc">+</div>
      </div>
      <div class="keypad__program-key">
        <div @click="tounchKey($event)" class="keypad__program-num">#</div>
      </div>
    </div>
    <div class="keypad__program-call">
      <a :href="enteredText.length > 0 ? 'tel:' + enteredText : null">
        <svg
          width="40px"
          fill="#fff"
          viewBox="0 0 32 32"
          version="1.1"
          xmlns="http://www.w3.org/2000/svg"
        >
          <g id="SVGRepo_bgCarrier" stroke-width="0"></g>
          <g id="SVGRepo_tracerCarrier" stroke-linecap="round" stroke-linejoin="round"></g>
          <g id="SVGRepo_iconCarrier">
            <title>phone</title>
            <path
              d="M0 10.375c0 0.938 0.344 1.969 0.781 3.063s1 2.125 1.438 2.906c1.188 2.063 2.719 4.094 4.469 5.781s3.813 3.094 6.125 3.938c1.344 0.531 2.688 1.125 4.188 1.125 0.75 0 1.813-0.281 2.781-0.688 0.938-0.406 1.781-1.031 2.094-1.781 0.125-0.281 0.281-0.656 0.375-1.094 0.094-0.406 0.156-0.813 0.156-1.094 0-0.156 0-0.313-0.031-0.344-0.094-0.188-0.313-0.344-0.563-0.5-0.563-0.281-0.656-0.375-1.5-0.875-0.875-0.5-1.781-1.063-2.563-1.469-0.375-0.219-0.625-0.313-0.719-0.313-0.5 0-1.125 0.688-1.656 1.438-0.563 0.75-1.188 1.438-1.625 1.438-0.219 0-0.438-0.094-0.688-0.25s-0.5-0.281-0.656-0.375c-2.75-1.563-4.594-3.406-6.156-6.125-0.188-0.313-0.625-0.969-0.625-1.313 0-0.406 0.563-0.875 1.125-1.375 0.531-0.469 1.094-1.031 1.094-1.719 0-0.094-0.063-0.375-0.188-0.781-0.281-0.813-0.656-1.75-0.969-2.656-0.156-0.438-0.281-0.75-0.313-0.906-0.063-0.094-0.094-0.219-0.125-0.375s-0.094-0.281-0.125-0.406c-0.094-0.281-0.25-0.5-0.406-0.625-0.156-0.063-0.531-0.156-0.906-0.188-0.375 0-0.813-0.031-1-0.031-0.094 0-0.219 0-0.344 0.031h-0.406c-1 0.438-1.719 1.313-2.25 2.344-0.5 1.031-0.813 2.188-0.813 3.219z"
            ></path>
          </g>
        </svg>
      </a>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      enteredText: "",
    };
  },
  methods: {
    tounchKey(event) {
      this.enteredText += event.srcElement.innerText;
    },
    enteredTextClear() {
      this.enteredText = this.enteredText.slice(0, -1);
    },
    enteredTextDelete() {
      this.enteredText = "";
    },
  },
};
</script>

<style scoped>
.keypad__program-keyboard {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  width: 250px;
  margin: 10px auto 20px;
  gap: 20px;
}

.keypad__program-clear {
  position: absolute;
  right: 38px;
  top: 110px;
}

.keypad__program-key {
  background-color: #2a2a2c;
  justify-content: center;
  flex-direction: column;
  align-items: center;
  border-radius: 50%;
  position: relative;
  cursor: pointer;
  display: flex;
  height: 70px;
  width: 70px;
}

.keypad__program-num {
  font-size: 32px;
  padding: 20px;
  margin-bottom: 10px;
}

.keypad__program-desc {
  font-size: 12px;
  position: absolute;
  bottom: 10px;
}

.keypad__program-call {
  background-color: #30d158;
  justify-content: center;
  align-items: center;
  border-radius: 50%;
  cursor: pointer;
  display: flex;
  height: 70px;
  margin: auto;
  width: 70px;
}

.keypad__program-call svg {
  margin-left: 12px;
}

.keypad__program-input {
  width: 100%;
  text-align: center;
  margin-top: 80px;
  font-size: 38px;
  background-color: transparent;
  border: none;
  outline: none;
  color: white;
}
</style>
