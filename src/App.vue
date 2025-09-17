<template>
  <div class="app">
    <Navbar />
    <HeroCarousel />
    <Contact />    
    <Plans />
    <Contact />
    <WhatsappButton />
  </div>
</template>

<script setup>
import Navbar from './components/Navbar.vue'
import HeroCarousel from './components/HeroCarousel.vue'
import Contact from './components/Contact.vue'
import Plans from './components/Plans.vue'
import WhatsappButton from './components/WhatsappButton.vue'

// Importa a logo do assets para usar como favicon
import logo from './assets/logo.png'

// Define favicon dinamicamente
const link = document.createElement('link')
link.rel = 'icon'
link.type = 'image/png'
link.href = logo
document.head.appendChild(link)
</script>

<style>
body {
  min-height: 100vh;
  background: #f8944c;
  background-blend-mode: overlay;
  margin: 0;
  padding: 0;
  width: 100%;
  overflow-x: hidden;
}

.app {
  width: 100%;
  font-family: 'Montserrat', sans-serif;
}
</style>
