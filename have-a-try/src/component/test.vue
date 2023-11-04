<template>
  <div class="container">
    <div class="logo" ref="logo">LOGO</div>
    <h1 ref="title">Welcome to Our Site</h1>
    <p ref="description">Discover the world of animations with us.</p>
  </div>
</template>

<script setup>
import { ref, onMounted } from 'vue';
import { gsap } from 'gsap';

const logo = ref(null);
const title = ref(null);
const description = ref(null);

onMounted(() => {
  const tl = gsap.timeline();

  tl.from(logo.value, { y: -30, opacity: 0, ease: 'back.out(1.7)', duration: 1.5 })
      .from(title.value, { y: -30, opacity: 0, ease: 'back.out(1.7)', duration: 1.5 }, "-=1")
      .from(description.value, { y: -30, opacity: 0, ease: 'back.out(1.7)', duration: 1.5 }, "-=1");
});
</script>

<style>
.container {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  height: 100vh;
  text-align: center;
}
.logo {
  font-size: 3rem;
  margin-bottom: 0.5em;
  color: #2c3e50;
  font-weight: bold;
  transform: translateY(-30px);
  opacity: 0;
}
h1 {
  font-size: 2rem;
  color: #34495e;
  transform: translateY(-30px);
  opacity: 0;
}
p {
  font-size: 1.25rem;
  color: #7f8c8d;
  transform: translateY(-30px);
  opacity: 0;
}
</style>
