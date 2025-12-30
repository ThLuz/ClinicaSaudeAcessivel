<template>
  <div class="app">
    <Navbar />
    <HeroCarousel />
    <WhyChoose />
    <BenefitsSection />
    <Plans />
    <Partners />
    <About />        
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
import Partners from './components/Partners.vue'
import About from './components/About.vue'
import WhyChoose from './components/WhyChoose.vue'

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
  overflow-x: hidden;
}

.app {
  font-family: 'Montserrat', sans-serif;
  max-width: 1280px;   /* controla o "espremer" */
  margin: 0 auto;      /* centraliza e cria laterais vazias */
  padding: 0 20px;     /* respiro interno */
}

* {
  box-sizing: border-box;
}


</style>
