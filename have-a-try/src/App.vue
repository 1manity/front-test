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
  background: #000;
}
.anim-test {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%,-50%);
  width: 100px;
  height: 100px;
  background: red;
  /* animation: anim 1s linear infinite; */
}
</style>
