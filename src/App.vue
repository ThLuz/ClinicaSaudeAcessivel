<template>
  <div class="app">
    <Navbar />
    <HeroCarousel />
    <WhyChoose />
    <BenefitsSection />
    <Plans />
    <About />        
    <Contact />
    <Footer />
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
import About from './components/About.vue'
import WhyChoose from './components/WhyChoose.vue'
import Footer from './components/Footer.vue'

import logo from './assets/favicon.png'

const link = document.createElement('link')
link.rel = 'icon'
link.type = 'image/png'
link.href = logo
document.head.appendChild(link)
</script>

<style>
html, body {
  width: 100%;
  max-width: 100%;
  overflow-x: hidden;
}

body {
  background: #f8944c;
  background-blend-mode: overlay;
  margin: 0;
}

.app {
  font-family: 'Montserrat', sans-serif;
  width: 100%;
  max-width: 1280px;   
  margin: 0 auto;
  padding: 0 20px;
  overflow-x: hidden;  
}

*,
*::before,
*::after {
  box-sizing: border-box;
  max-width: 100%;
}

img,
video,
iframe {
  max-width: 100%;
  height: auto;
  display: block;
}

@media (max-width: 912px) {
  .app {
    max-width: none;    
    width: 100%;
    padding: 0;
    margin: 0;
    overflow-x: hidden;
  }

  body{
    background-color: #FFF;
  }
}
</style>
