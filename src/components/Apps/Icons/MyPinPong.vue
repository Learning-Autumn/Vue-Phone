<template>
  <div>
    <svg @click="openApp" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" width="48px" height="48px"
      viewBox="0 0 48 48" version="1.1">
      <g id="surface1">
        <path style=" stroke:none;fill-rule:nonzero;fill:rgb(100%,100%,100%);fill-opacity:1;"
          d="M 12 0 L 36 0 C 42.628906 0 48 5.371094 48 12 L 48 36 C 48 42.628906 42.628906 48 36 48 L 12 48 C 5.371094 48 0 42.628906 0 36 L 0 12 C 0 5.371094 5.371094 0 12 0 Z M 12 0 " />
        <path
          style="fill-rule:nonzero;fill:rgb(100%,0%,0%);fill-opacity:1;stroke-width:1;stroke-linecap:butt;stroke-linejoin:miter;stroke:rgb(100%,0%,0%);stroke-opacity:1;stroke-miterlimit:4;"
          d="M 133.098513 211.838172 C 137.726722 243.334036 127.147958 275.310753 104.607979 297.850731 L 21.841177 380.617534 C 4.470367 397.988344 4.470367 426.118238 21.901284 443.489048 C 39.211987 460.859858 67.401988 460.799752 84.712691 443.489048 L 167.479494 360.662139 C 190.019473 338.12216 221.936083 327.603504 253.492053 332.231713 C 267.977746 334.335444 282.884185 334.275337 297.850731 332.412032 L 132.918193 167.479494 C 131.054888 182.44604 130.994781 197.352479 133.098513 211.838172 Z M 133.098513 211.838172 "
          transform="matrix(0.0649887,0,0,0.0649887,7.783695,7.783695)" />
        <path
          style="fill-rule:nonzero;fill:rgb(100%,0%,0%);fill-opacity:1;stroke-width:1;stroke-linecap:butt;stroke-linejoin:miter;stroke:rgb(100%,0%,0%);stroke-opacity:1;stroke-miterlimit:4;"
          d="M 423.77408 41.496039 C 362.94619 -19.331851 257.459089 -12.479697 188.156168 56.823224 C 172.408236 72.571156 160.026274 90.2425 150.769856 108.755336 L 356.57489 314.500262 C 375.087726 305.303951 392.759069 292.921989 408.507001 277.174058 C 477.809923 207.871136 484.662076 102.384035 423.77408 41.496039 Z M 423.77408 41.496039 "
          transform="matrix(0.0649887,0,0,0.0649887,7.783695,7.783695)" />
        <path
          style="fill-rule:nonzero;fill:rgb(100%,0%,0%);fill-opacity:1;stroke-width:1;stroke-linecap:butt;stroke-linejoin:miter;stroke:rgb(100%,0%,0%);stroke-opacity:1;stroke-miterlimit:4;"
          d="M 434.533163 387.650007 C 403.758579 387.650007 378.814335 412.59425 378.814335 443.368835 C 378.814335 474.143419 403.758579 499.027556 434.533163 499.027556 C 465.247641 499.027556 490.191884 474.143419 490.191884 443.368835 C 490.191884 412.59425 465.247641 387.650007 434.533163 387.650007 Z M 434.533163 387.650007 "
          transform="matrix(0.0649887,0,0,0.0649887,7.783695,7.783695)" />
      </g>
    </svg>

  </div>
</template>

<script>
export default {
  inject: ['setProgram'],
  methods: {
    openApp() {
      this.setProgram('PinPong');
    }
  }
};
</script>

<style lang="scss" scoped></style>