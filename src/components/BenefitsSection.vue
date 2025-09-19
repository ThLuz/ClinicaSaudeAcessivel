<template>
  <section class="services-carousel">
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
      <button class="prev" @click="prevSlide">
        <span>←</span>
      </button>
      <button class="next" @click="nextSlide">
        <span>→</span>
      </button>
    </div>
  </section>
</template>

<script setup>
import services1 from '../assets/services1.jpg'
import services2 from '../assets/services2.jpg'
import services3 from '../assets/services3.jpg'
import services4 from '../assets/services4.jpg'
import services5 from '../assets/services5.jpg'
import services6 from '../assets/services6.jpg'

const services = [
  { image: services1, title: 'MÉDICOS', desc: 'Consultas com médicos especializados para cuidar da sua saúde.' },
  { image: services2, title: 'DENTISTAS', desc: 'Atendimento odontológico completo para o seu sorriso.' },
  { image: services3, title: 'EXAMES', desc: 'Diversos exames para diagnóstico rápido e preciso.' },
  { image: services4, title: 'ESTÉTICA CORPORAL', desc: 'Tratamentos para realçar sua beleza e bem-estar.' },
  { image: services5, title: 'HARMONIZAÇÃO FACIAL', desc: 'Procedimentos estéticos para equilíbrio e rejuvenescimento.' },
  { image: services6, title: 'PLANOS ACESSÍVEIS', desc: 'Opções de planos de saúde e estética para todos.' },
]

function nextSlide() {
  const list = document.querySelector('.services-list')
  list.scrollBy({ left: 320, behavior: 'smooth' })
}

function prevSlide() {
  const list = document.querySelector('.services-list')
  list.scrollBy({ left: -320, behavior: 'smooth' })
}
</script>

<style scoped>
.services-carousel {
  padding: 40px 20px;
  background: #eee;
  text-align: center;
  font-family: 'Montserrat', sans-serif;
}

.services-list {
  display: flex;
  gap: 20px;
  overflow-x: auto;
  scroll-behavior: smooth;
  -webkit-overflow-scrolling: touch;
  padding-bottom: 10px;
}

.service-card {
  flex: 0 0 280px;
  background: #eee;
  border-radius: 12px;
  border: 1px solid #555;
  box-shadow: 0 8px 20px rgba(0,0,0,0.1);
  text-align: left;
  overflow: hidden;
  transition: transform 0.3s ease;
}

.service-card img {
  width: 100%;
  height: 160px;
  object-fit: cover;
  border-bottom: 5px solid #eb9321;
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
  text-align: center;
  margin: 0 auto 60px;
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
  border: none;
  color: #555;
  border: 2px solid #555;
  font-size: 24px;
  width: 50px;
  height: 50px;
  border-radius: 50%;
  cursor: pointer;
  transition: all 0.3s ease;
  display: flex;
  align-items: center;
  justify-content: center;
  box-shadow: 0 4px 10px rgba(0,0,0,0.15);
}

.services-controls span {
  display: block;
  line-height: 1;
  margin-top: -2px; /* centraliza a seta verticalmente */
}

/* Remove scrollbar */
.services-list::-webkit-scrollbar {
  display: none;
}
</style>
