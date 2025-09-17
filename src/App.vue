<template>
  <div class="app">
    <Navbar />
    <HeroCarousel />
    <Plans />
    <Contact />
  </div>
</template>

<script setup>
import Navbar from './components/Navbar.vue'
import HeroCarousel from './components/HeroCarousel.vue'
import Contact from './components/Contact.vue';
import Plans from './components/Plans.vue';
</script>

<style>
body {
  min-height: 100vh;
  background:
    radial-gradient(circle at 70% 85%, rgba(255, 212, 185, 0.45) 0%, transparent 12%),
    linear-gradient(120deg, #ff7f32 0%, #ffa34d 30%, #ffb876 55%, #ff8c3c 100%);
  background-blend-mode: overlay;
  margin: 0;
}

</style>
