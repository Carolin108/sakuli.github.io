<template>
  <svg
    class="sakuli-circle"
    version="1.1"
    id="Ebene_1"
    xmlns="http://www.w3.org/2000/svg"
    xmlns:xlink="http://www.w3.org/1999/xlink"
    x="0px"
    y="0px"
    viewBox="0 0 283.46 283.46"
    enable-background="new 0 0 283.46 283.46"
    xml:space="preserve"
  >
    <path
      class
      fill="#95C11F"
      d="M141.41,1.31C64.04,1.31,1.09,64.25,1.09,141.62s62.95,140.32,140.31,140.32
	c77.37,0,140.31-62.95,140.31-140.32S218.78,1.31,141.41,1.31z M131.87,118.32c5.85,3.75,7.55,11.52,3.8,17.37
	c-2.4,3.75-6.46,5.79-10.6,5.79c-2.32,0-4.67-0.64-6.77-1.99l-39.43-25.27c-6.65-4.26-10.62-11.52-10.62-19.43
	c0-7.9,3.97-15.17,10.63-19.43L118.3,50.1c5.85-3.75,13.63-2.04,17.37,3.8c3.75,5.85,2.05,13.63-3.8,17.37L95.17,94.8L131.87,118.32
	z M204.75,203.85l-39.43,25.27c-2.1,1.35-4.45,1.99-6.77,1.99c-4.14,0-8.2-2.04-10.6-5.79c-3.75-5.85-2.05-13.63,3.8-17.37
	l36.7-23.52l-36.7-23.52c-5.85-3.75-7.55-11.52-3.8-17.37c3.74-5.85,11.53-7.55,17.37-3.8l39.43,25.27
	c6.65,4.26,10.62,11.53,10.62,19.43C215.37,192.32,211.4,199.59,204.75,203.85z"
    ></path>
  </svg>
</template>
<script lang="ts">
import Vue from "vue";
export default Vue.extend({});
</script>
<style lang="scss" scoped>
svg {
    align-self: center;
}
@keyframes spin {
  to {
    transform: rotate(360deg);
  }
}

.sakuli-circle {
  max-width: 30px;
  animation: spin 3s linear infinite;

}
</style>


