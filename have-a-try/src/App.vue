<template>
  <div class="container">
    <div ref="box" class="anim-test" @click="boxAnim">

    </div>
  </div>
</template>
<script setup>
import {onMounted, ref} from 'vue';
import { gsap } from 'gsap';
import Test from "./component/test.vue";
import Logo from "./assets/logo.png"

const box = ref(null);
const boxAnim =()=> {gsap.to(box.value, { x: 100, duration: 2 });}

onMounted(() => {

});
</script>
<style scoped>
.container {
  position: relative;
  width: 100%;
  height: 100%;
  background: #2980B9;  /* fallback for old browsers */
  background: -webkit-linear-gradient(to right, #FFFFFF, #6DD5FA, #2980B9);  /* Chrome 10-25, Safari 5.1-6 */
  background: linear-gradient(to right top, #FFFFFF, #6DD5FA, #2980B9); /* W3C, IE 10+/ Edge, Firefox 16+, Chrome 26+, Opera 12+, Safari 7+ */

}
.anim-test {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%,-50%);
  width: 500px;
  height: 500px;
  background-image: url("./assets/logo.png");
  background-repeat: no-repeat;
  background-size: contain;

}
</style>
