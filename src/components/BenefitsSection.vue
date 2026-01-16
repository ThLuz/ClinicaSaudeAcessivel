<template>
  <section id="services" class="services-carousel">
    <div class="badge-title">SERVIÇOS ESPECIALIZADOS PARA VOCÊ</div>

    <div class="services-list">
      <div 
        class="service-card" 
        v-for="(service, index) in services" 
        :key="index"
      >
        <img :src="service.image" :alt="service.title" />
        <div class="service-info">
          <h3>{{ service.title }}</h3>
          <p>{{ service.desc }}</p>
        </div>
      </div>
    </div>

    <div class="services-controls">
      <button class="prev" @click="prevSlide">←</button>
      <button class="next" @click="nextSlide">→</button>
    </div>
  </section>
</template>

<script setup>
import services2 from '../assets/services1.jpg'
import services1 from '../assets/services2.jpg'
import services3 from '../assets/services3.jpg'
import services4 from '../assets/services4.jpg'
import services5 from '../assets/services5.jpg'
import services6 from '../assets/services6.jpg'
import services7 from '../assets/services7.jpg'
import services8 from '../assets/services8.jpg'
import services9 from '../assets/services9.jpg'
import services10 from '../assets/services10.jpg'


const services = [
  { image: services1, title: 'DENTISTAS', desc: 'Atendimento odontológico completo para o seu sorriso.' },
  { image: services8, title: 'PSICOLOGIA', desc: 'Cuidado com a saúde mental e bem-estar emocional.' },
  { image: services9, title: 'NUTRIÇÃO', desc: 'Acompanhamento nutricional para uma vida mais saudável.' },
  { image: services10, title: 'FISIOTERAPIA', desc: 'Reabilitação e prevenção para sua qualidade de vida.' },
  { image: services2, title: 'DEPILAÇÃO A LASER', desc: 'Tecnologia avançada para remoção de pelos com conforto e eficácia.' },
  { image: services7, title: 'REMOÇÃO TATUAGEM', desc: 'Procedimentos seguros e modernos para remoção de tatuagens.' },
  { image: services3, title: 'EXAMES', desc: 'Diversos exames para diagnóstico rápido e preciso.' },
  { image: services4, title: 'ESTÉTICA CORPORAL', desc: 'Tratamentos para realçar sua beleza e bem-estar.' },
  { image: services5, title: 'HARMONIZAÇÃO FACIAL', desc: 'Procedimentos estéticos para equilíbrio e rejuvenescimento.' },
  { image: services6, title: 'PLANOS ACESSÍVEIS', desc: 'Opções de planos de saúde e estética para todos.' },
]

function nextSlide() {
  const list = document.querySelector('.services-list')
  const card = list.querySelector('.service-card')
  const gap = parseInt(getComputedStyle(list).gap) || 0
  const scrollAmount = card.offsetWidth + gap
  list.scrollBy({ left: scrollAmount, behavior: 'smooth' })
}

function prevSlide() {
  const list = document.querySelector('.services-list')
  const card = list.querySelector('.service-card')
  const gap = parseInt(getComputedStyle(list).gap) || 0
  const scrollAmount = card.offsetWidth + gap
  list.scrollBy({ left: -scrollAmount, behavior: 'smooth' })
}
</script>

<style scoped>
.services-carousel {
  padding: 40px 20px;
  background: #eee;
  font-family: 'Montserrat', sans-serif;
  text-align: center;
  overflow: hidden; 
  box-sizing: border-box;
  width: 100%;
  max-width: 100vw; 
}

.badge-title {
  position: relative;
  display: inline-block;
  background-color: #555;
  color: white;
  font-weight: 700;
  font-size: 24px;
  padding: 12px 24px 12px 36px;
  border-radius: 2px;
  margin: 0 auto 60px;
  text-align: center;
  box-sizing: border-box;
}

.badge-title::before {
  content: "";
  position: absolute;
  left: 0;
  top: 0;
  width: 0;
  height: 0;
  border-top: 18px solid transparent;
  border-bottom: 18px solid transparent;
  border-right: 18px solid #555;
  transform: translateX(-80%);
  margin-top: 12px;
}

.services-list {
  display: flex;
  gap: 20px;
  overflow-x: hidden;
  scroll-behavior: smooth;
  -webkit-overflow-scrolling: touch;
  width: 100%;
  max-width: 100%;
  padding-bottom: 10px;
  box-sizing: border-box;
}

.service-card {
  flex: 0 0 auto;
  max-width: 280px;
  background: #eee;
  border-radius: 12px;
  border: 1px solid #555;
  box-shadow: 0 8px 20px rgba(0,0,0,0.1);
  text-align: left;
  overflow: hidden;
  transition: transform 0.3s ease;
  box-sizing: border-box;
}

.service-card img {
  width: 100%;
  height: 160px;
  object-fit: cover;
  border-bottom: 5px solid #eb9321;
}

.service-info {
  padding: 15px;
  text-align: center;
}

.service-info h3 {
  font-size: 20px;
  margin-bottom: 5px;
  color: #333;
}

.service-info p {
  font-size: 14px;
  color: #555;
}

.services-controls {
  display: flex;
  justify-content: center;
  margin-top: 25px;
  gap: 20px;
}

.services-controls button {
  background: #eee;
  border: 2px solid #555;
  color: #555;
  font-size: 24px;
  width: 50px;
  height: 50px;
  border-radius: 50%;
  cursor: pointer;
  display: flex;
  align-items: center;
  justify-content: center;
  box-shadow: 0 4px 10px rgba(0,0,0,0.15);
  transition: all 0.3s ease;
}

.services-controls span {
  display: block;
  line-height: 1;
  margin-top: -2px;
}

.services-list::-webkit-scrollbar {
  display: none;
}

@media (max-width: 912px) {
  .services-carousel {
    padding: 25px 10px;
  }

  .badge-title {
    font-size: 18px;
    padding: 10px 16px 10px 26px;
    margin-bottom: 30px;
    max-width: 90%;
  }

  .badge-title h2 {
    font-size: 10px;
  }

  .badge-title::before {
    border-top: 14px solid transparent;
    border-bottom: 14px solid transparent;
    border-right: 14px solid #555;
    margin-top: 10px;
  }

  .services-list {
    overflow-x: auto;
    gap: 15px;
    padding-bottom: 10px;
  }

  .service-card {
    flex: 0 0 320px;
    max-width: 320px;
  }

  .service-card img {
    height: 140px;
  }

  .service-info h3 {
    font-size: 16px;
  }

  .service-info p {
    font-size: 12px;
    line-height: 1.3;
  }

  .services-controls {
    display: none;
  }
}

</style>

