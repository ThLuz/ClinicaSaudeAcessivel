<template>
  <div class="app">
    <Navbar />
    <HeroCarousel />
    <BenefitsSection />
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
import BenefitsSection from './components/BenefitsSection.vue'

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
  background: #f8944c;
  background-blend-mode: overlay;
  margin: 0;
}

.app {
  font-family: 'Montserrat', sans-serif;
}
</style>
