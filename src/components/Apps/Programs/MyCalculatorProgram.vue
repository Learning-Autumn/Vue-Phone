<template>
  <div class="calculator__program">
    <svg
      @click="showHistory = !showHistory"
      class="calculator__program-history"
      xmlns="http://www.w3.org/2000/svg"
      xmlns:xlink="http://www.w3.org/1999/xlink"
      width="18px"
      height="18px"
      viewBox="0 0 18 18"
      version="1.1"
    >
      <g id="surface1">
        <path
          style="
            fill-rule: nonzero;
            fill: rgb(100%, 62.352943%, 3.921569%);
            fill-opacity: 1;
            stroke-width: 1.05104;
            stroke-linecap: square;
            stroke-linejoin: round;
            stroke: rgb(100%, 62.352943%, 3.921569%);
            stroke-opacity: 1;
            stroke-miterlimit: 4;
          "
          d="M 116.870117 533.96319 C 116.870117 498.096817 86.771484 468.116909 51.06356 468.116909 C 15.355637 468.116909 -14.606184 498.096817 -14.606184 533.96319 C -14.606184 569.692669 15.355637 599.672577 51.06356 599.672577 C 86.771484 599.672577 116.870117 569.692669 116.870117 533.96319 Z M 116.870117 533.96319 "
          transform="matrix(0.028552,0,0,0.0285347,0.417035,0.365064)"
        />
        <path
          style="
            fill-rule: nonzero;
            fill: rgb(100%, 62.352943%, 3.921569%);
            fill-opacity: 1;
            stroke-width: 1.05104;
            stroke-linecap: square;
            stroke-linejoin: round;
            stroke: rgb(100%, 62.352943%, 3.921569%);
            stroke-opacity: 1;
            stroke-miterlimit: 4;
          "
          d="M 116.870117 302.611392 C 116.870117 266.881913 86.771484 236.765111 51.06356 236.765111 C 15.355637 236.765111 -14.606184 266.881913 -14.606184 302.611392 C -14.606184 338.340871 15.355637 368.457673 51.06356 368.457673 C 86.771484 368.457673 116.870117 338.340871 116.870117 302.611392 Z M 116.870117 302.611392 "
          transform="matrix(0.028552,0,0,0.0285347,0.417035,0.365064)"
        />
        <path
          style="
            fill-rule: nonzero;
            fill: rgb(100%, 62.352943%, 3.921569%);
            fill-opacity: 1;
            stroke-width: 1.05104;
            stroke-linecap: square;
            stroke-linejoin: round;
            stroke: rgb(100%, 62.352943%, 3.921569%);
            stroke-opacity: 1;
            stroke-miterlimit: 4;
          "
          d="M 116.870117 71.259593 C 116.870117 35.530115 86.771484 5.550207 51.06356 5.550207 C 15.355637 5.550207 -14.606184 35.530115 -14.606184 71.259593 C -14.606184 107.125967 15.355637 137.105875 51.06356 137.105875 C 86.771484 137.105875 116.870117 107.125967 116.870117 71.259593 Z M 116.870117 71.259593 "
          transform="matrix(0.028552,0,0,0.0285347,0.417035,0.365064)"
        />
        <path
          style="
            fill-rule: nonzero;
            fill: rgb(100%, 62.352943%, 3.921569%);
            fill-opacity: 1;
            stroke-width: 1.05103;
            stroke-linecap: round;
            stroke-linejoin: miter;
            stroke: rgb(100%, 62.352943%, 3.921569%);
            stroke-opacity: 1;
            stroke-miterlimit: 4;
          "
          d="M 211.543999 21.56687 C 185.276101 21.56687 164.070246 43.880682 164.070246 71.259593 C 164.070246 98.775399 185.276101 121.089212 211.543999 121.089212 L 568.212799 121.089212 C 594.480697 121.089212 615.823364 98.775399 615.823364 71.259593 C 615.823364 43.880682 594.480697 21.56687 568.212799 21.56687 Z M 211.543999 21.56687 "
          transform="matrix(0.028552,0,0,0.0285347,0.417035,0.365064)"
        />
        <path
          style="
            fill-rule: nonzero;
            fill: rgb(100%, 62.352943%, 3.921569%);
            fill-opacity: 1;
            stroke-width: 1.05103;
            stroke-linecap: round;
            stroke-linejoin: miter;
            stroke: rgb(100%, 62.352943%, 3.921569%);
            stroke-opacity: 1;
            stroke-miterlimit: 4;
          "
          d="M 211.543999 252.781774 C 185.276101 252.781774 164.070246 275.095586 164.070246 302.611392 C 164.070246 330.127198 185.276101 352.44101 211.543999 352.44101 L 568.212799 352.44101 C 594.480697 352.44101 615.823364 330.127198 615.823364 302.611392 C 615.823364 275.095586 594.480697 252.781774 568.212799 252.781774 Z M 211.543999 252.781774 "
          transform="matrix(0.028552,0,0,0.0285347,0.417035,0.365064)"
        />
        <path
          style="
            fill-rule: nonzero;
            fill: rgb(100%, 62.352943%, 3.921569%);
            fill-opacity: 1;
            stroke-width: 1.05103;
            stroke-linecap: round;
            stroke-linejoin: miter;
            stroke: rgb(100%, 62.352943%, 3.921569%);
            stroke-opacity: 1;
            stroke-miterlimit: 4;
          "
          d="M 211.543999 484.133572 C 185.276101 484.133572 164.070246 506.447385 164.070246 533.96319 C 164.070246 561.342101 185.276101 583.655914 211.543999 583.655914 L 568.212799 583.655914 C 594.480697 583.655914 615.823364 561.342101 615.823364 533.96319 C 615.823364 506.447385 594.480697 484.133572 568.212799 484.133572 Z M 211.543999 484.133572 "
          transform="matrix(0.028552,0,0,0.0285347,0.417035,0.365064)"
        />
      </g>
    </svg>
    <div class="calculator__program-inner">
      <div class="calculator__program-display">
        <ul v-if="this.showHistory" class="calculator__history-list">
          <li
            class="calculator__history-item"
            v-for="(hist, i) in this.historyOperation"
            v-bind:key="i"
          >
            {{ hist[0] }} {{ hist[1] }} {{ hist[2] }} = {{ hist[3] }}
          </li>
        </ul>
        <input
          v-if="!isOperation"
          class="calculator__program-display--input"
          v-model="resultNumber"
          :placeholder="resultNumber === '' ? '0' : ''"
          type=""
          name=""
          value=""
        />
        <input
          v-else
          class="calculator__program-display--input"
          v-model="nextNumber"
          :placeholder="nextNumber === '' ? '0' : ''"
          type=""
          name=""
          value=""
        />
        <!-- <label class="calculator__program-display--label" for="">0.77734</label> -->
      </div>
      <div class="calculator__program-controls">
        <button
          @dblclick="clearHistory"
          @click="clearNumber"
          class="calculator__program-control-btn calculator__program-control-btn--gray"
          type=""
        >
          AC
        </button>
        <button
          @click="signNumber"
          data-type="+/-"
          class="calculator__program-control-btn calculator__program-control-btn--gray"
          type=""
        >
          +/-
        </button>
        <button
          @click="procOperation($event)"
          data-type="%"
          class="calculator__program-control-btn calculator__program-control-btn--gray"
          type=""
        >
          %
        </button>
        <button
          @click="procOperation($event)"
          data-type="/"
          class="calculator__program-control-btn calculator__program-control-btn--orange"
          type=""
        >
          <svg
            fill="#fff"
            version="1.1"
            id="Layer_1"
            xmlns="http://www.w3.org/2000/svg"
            xmlns:xlink="http://www.w3.org/1999/xlink"
            viewBox="0 0 472.615 472.615"
            xml:space="preserve"
            width="32px"
            height="32px"
            stroke="#fff"
            stroke-width="0.00472615"
          >
            <g id="SVGRepo_bgCarrier" stroke-width="0" />
            <g
              id="SVGRepo_tracerCarrier"
              stroke-linecap="round"
              stroke-linejoin="round"
            />
            <g id="SVGRepo_iconCarrier">
              <g>
                <g>
                  <rect y="226.462" width="472.615" height="19.692" />
                </g>
              </g>
              <g>
                <g>
                  <circle cx="236.288" cy="96.788" r="66.56" />
                </g>
              </g>
              <g>
                <g>
                  <path
                    d="M236.29,309.268c-36.726,0-66.56,29.932-66.56,66.56c0,36.726,29.834,66.56,66.56,66.56 c36.726,0,66.56-29.834,66.56-66.56C302.85,339.2,273.016,309.268,236.29,309.268z"
                  />
                </g>
              </g>
            </g>
          </svg>
        </button>
        <button
          @click="enteringNumbers($event)"
          class="calculator__program-control-btn calculator__program-control-btn--black"
          type=""
        >
          7
        </button>
        <button
          @click="enteringNumbers($event)"
          class="calculator__program-control-btn calculator__program-control-btn--black"
          type=""
        >
          8
        </button>
        <button
          @click="enteringNumbers($event)"
          class="calculator__program-control-btn calculator__program-control-btn--black"
          type=""
        >
          9
        </button>
        <button
          @click="procOperation($event)"
          data-type="*"
          class="calculator__program-control-btn calculator__program-control-btn--orange"
          type=""
        >
          X
        </button>
        <button
          @click="enteringNumbers($event)"
          class="calculator__program-control-btn calculator__program-control-btn--black"
          type=""
        >
          4
        </button>
        <button
          @click="enteringNumbers($event)"
          class="calculator__program-control-btn calculator__program-control-btn--black"
          type=""
        >
          5
        </button>
        <button
          @click="enteringNumbers($event)"
          class="calculator__program-control-btn calculator__program-control-btn--black"
          type=""
        >
          6
        </button>
        <button
          @click="procOperation($event)"
          data-type="-"
          class="calculator__program-control-btn calculator__program-control-btn--orange"
          type=""
        >
          —
        </button>
        <button
          @click="enteringNumbers($event)"
          class="calculator__program-control-btn calculator__program-control-btn--black"
          type=""
        >
          1
        </button>
        <button
          @click="enteringNumbers($event)"
          class="calculator__program-control-btn calculator__program-control-btn--black"
          type=""
        >
          2
        </button>
        <button
          @click="enteringNumbers($event)"
          class="calculator__program-control-btn calculator__program-control-btn--black"
          type=""
        >
          3
        </button>
        <button
          @click="procOperation($event)"
          data-type="+"
          class="calculator__program-control-btn calculator__program-control-btn--orange"
          type=""
        >
          +
        </button>
        <button
          class="calculator__program-control-btn calculator__program-control-btn--black"
          type=""
        >
          <svg
            width="40px"
            height="40px"
            viewBox="0 0 32 32"
            xmlns="http://www.w3.org/2000/svg"
            fill="#2a2a2c"
            stroke="#2a2a2c"
          >
            <g id="SVGRepo_bgCarrier" stroke-width="0" />
            <g
              id="SVGRepo_tracerCarrier"
              stroke-linecap="round"
              stroke-linejoin="round"
            />
            <g id="SVGRepo_iconCarrier">
              <g fill="none" fill-rule="evenodd">
                <path d="m0 0h32v32h-32z" />
                <path
                  d="m24.5 0c2.209139 0 4 1.790861 4 4v24c0 2.209139-1.790861 4-4 4h-17c-2.209139 0-4-1.790861-4-4v-24c0-2.209139 1.790861-4 4-4zm-14.5 24c-.82842712 0-1.5.6715729-1.5 1.5s.67157288 1.5 1.5 1.5c.8284271 0 1.5-.6715729 1.5-1.5s-.6715729-1.5-1.5-1.5zm6 0c-.8284271 0-1.5.6715729-1.5 1.5s.6715729 1.5 1.5 1.5 1.5-.6715729 1.5-1.5-.6715729-1.5-1.5-1.5zm6 0c-.8284271 0-1.5.6715729-1.5 1.5s.6715729 1.5 1.5 1.5 1.5-.6715729 1.5-1.5-.6715729-1.5-1.5-1.5zm-12-6c-.82842712 0-1.5.6715729-1.5 1.5s.67157288 1.5 1.5 1.5c.8284271 0 1.5-.6715729 1.5-1.5s-.6715729-1.5-1.5-1.5zm6 0c-.8284271 0-1.5.6715729-1.5 1.5s.6715729 1.5 1.5 1.5 1.5-.6715729 1.5-1.5-.6715729-1.5-1.5-1.5zm6 0c-.8284271 0-1.5.6715729-1.5 1.5s.6715729 1.5 1.5 1.5 1.5-.6715729 1.5-1.5-.6715729-1.5-1.5-1.5zm-12-6c-.82842712 0-1.5.6715729-1.5 1.5s.67157288 1.5 1.5 1.5c.8284271 0 1.5-.6715729 1.5-1.5s-.6715729-1.5-1.5-1.5zm6 0c-.8284271 0-1.5.6715729-1.5 1.5s.6715729 1.5 1.5 1.5 1.5-.6715729 1.5-1.5-.6715729-1.5-1.5-1.5zm6 0c-.8284271 0-1.5.6715729-1.5 1.5s.6715729 1.5 1.5 1.5 1.5-.6715729 1.5-1.5-.6715729-1.5-1.5-1.5zm1.5-9h-15c-1.1045695 0-2 .8954305-2 2v2c0 1.1045695.8954305 2 2 2h15c1.1045695 0 2-.8954305 2-2v-2c0-1.1045695-.8954305-2-2-2z"
                  fill="#ffff"
                />
              </g>
            </g>
          </svg>
        </button>
        <button
          @click="enteringNumbers($event)"
          class="calculator__program-control-btn calculator__program-control-btn--black"
          type=""
        >
          0
        </button>
        <button
          data-type="."
          class="calculator__program-control-btn calculator__program-control-btn--black"
          type=""
        >
          .
        </button>
        <button
          @click="procOperation($event)"
          data-type="="
          class="calculator__program-control-btn calculator__program-control-btn--orange"
          type=""
        >
          =
        </button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      resultNumber: "",
      nextNumber: "",
      isOperation: "",
      showHistory: false,
      historyOperation: [],
    };
  },
  methods: {
    enteringNumbers(event) {
      let numberPressed = event.target.innerText;
      if (!this.isOperation) {
        this.resultNumber += numberPressed;
      } else {
        this.nextNumber += numberPressed;
      }
    },
    enteringOperation(operation) {
      if (operation !== "=") this.isOperation = operation;
    },
    clearNumber() {
      this.resultNumber = "";
      this.nextNumber = "";
      this.isOperation = "";
    },
    clearHistory() {
      this.historyOperation = [];
    },
    calcInterest(numOne, numTwo) {
      return (numOne / numTwo) * 100;
    },
    procOperation(event) {
      let operPressed = event.currentTarget.getAttribute("data-type");

      this.enteringOperation(operPressed);

      if (operPressed === "=") {
        const operations = {
          "+": (a, b) => a + b,
          "-": (a, b) => a - b,
          "*": (a, b) => a * b,
          "/": (a, b) => a / b,
          "%": (a, b) => this.calcInterest(b, a),
        };
        if (operations[this.isOperation]) {
          let resultNumber = operations[this.isOperation](
            Number(this.resultNumber),
            Number(this.nextNumber)
          );
          let decimals = 3;
          let factor = Math.pow(10, decimals);
          let roundedNum = Math.round(resultNumber * factor) / factor;

          this.historyOperation.push([
            this.resultNumber,
            this.isOperation,
            this.nextNumber,
            roundedNum,
          ]);
          this.resultNumber = roundedNum;
        }
        this.isOperation = "";
        this.nextNumber = "";
      }
    },
    signNumber() {
      if (!this.isOperation) {
        this.resultNumber = -Number(this.resultNumber);
      } else {
        this.nextNumber = -Number(this.nextNumber);
      }
    },
  },
};
</script>

<style scoped>
.calculator__program {
  width: 320px;
  height: 695px;
  position: relative;
}

.calculator__program-history {
  position: absolute;
  left: 5px;
  top: 55px;
  cursor: pointer;
}

.calculator__program-inner {
  display: flex;
  height: 100%;
  flex-direction: column;
  justify-content: end;
  padding-bottom: 30px;
  padding: 0 10px 30px;
}

.calculator__history-list {
  list-style: none;
}

.calculator__history-item {
  color: #5c5c5f;
  font-size: 20px;
}

.calculator__program-display {
  margin-bottom: 20px;
  text-align: end;
}

.calculator__program-display--label {
  font-size: 60px;
}

.calculator__program-display--input {
  font-size: 60px;
  background-color: transparent;
  border: none;
  color: #fff;
  text-align: end;
  outline: none;
  width: 100%;
}

.calculator__program-display--input::placeholder {
  font-size: 60px;
  color: #fff;
}

.calculator__program-controls {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  grid-template-rows: repeat(5, 1fr);
  gap: 5px;
}

.calculator__program-control-btn {
  width: 70px;
  height: 70px;
  border-radius: 50%;
  border: none;
  color: #fff;
  font-size: 32px;
  display: flex;
  justify-content: center;
  align-items: center;
}

.calculator__program-control-btn--gray {
  background-color: #5c5c5f;
}

.calculator__program-control-btn--black {
  background-color: #2a2a2c;
}

.calculator__program-control-btn--orange {
  background-color: #ff9f0a;
}
</style>
