<template>
  <section id="servicos" class="benefits-section">
    <div class="badge-title">SERVIÇOS ESPECIALIZADOS PARA VOCÊ</div>
    <div class="benefits-grid">
      <div class="benefit-item" v-for="(benefit, index) in benefits" :key="index">
        <div class="benefit-image">
          <img :src="benefit.image" :alt="benefit.title" />
        </div>
        <h3 class="benefit-title">{{ benefit.title }}</h3>
        <p class="benefit-description">{{ benefit.description }}</p>
      </div>
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

const benefits = [
  { image: services1, title: 'MÉDICOS', description: 'Consultas com médicos especializados para cuidar da sua saúde.' },
  { image: services2, title: 'DENTISTAS', description: 'Atendimento odontológico completo para o seu sorriso.' },
  { image: services3, title: 'EXAMES', description: 'Diversos exames para diagnóstico rápido e preciso.' },
  { image: services4, title: 'ESTÉTICA CORPORAL', description: 'Tratamentos para realçar sua beleza e bem-estar.' },
  { image: services5, title: 'HARMONIZAÇÃO FACIAL', description: 'Procedimentos estéticos para equilíbrio e rejuvenescimento.' },
  { image: services6, title: 'PLANOS ACESSÍVEIS', description: 'Opções de planos de saúde e estética para todos.' }
]
</script>

<style scoped>

* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

/* Previne scroll lateral */
:host, .benefits-section {
  overflow-x: hidden;
  width: 100%;
}

.benefits-section {
  padding: 40px 40px; /* menos padding lateral */
  background: #eeeeee;
  text-align: center;
  box-sizing: border-box;
    box-shadow: 0 10px 30px rgba(0,0,0,0.2);
}

.section-title {
  font-size: 26px;
  color: #333;
  font-weight: bold;
  margin-bottom: 30px;
}

.benefits-grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 20px;
  max-width: 1200px;
  width: 100%; /* garante que nunca extrapole */
  margin: 0 auto;
  box-sizing: border-box;
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
  margin: 0 auto 50px;
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

.benefit-image img {
  width: 100%;
  max-width: 100%; /* evita overflow */
  height: 240px;
  object-fit: cover;
  border-bottom: 6px solid #555;
}

.benefit-title {
  color: #555;
  font-size: 24px;
  font-weight: 700;
  margin-top: 5px;
  margin-bottom: 0;
}

.benefit-description {
  color: #555;
  font-size: 16px;
  padding: 0 10px 10px;
  margin-top: 0;
}

/* Responsivo */
@media (max-width: 1024px) {
  .benefits-grid {
    grid-template-columns: repeat(2, 1fr);
  }
  .benefits-section {
    padding: 30px 20px; /* padding menor em telas médias */
  }
}

@media (max-width: 600px) {
  .benefits-grid {
    grid-template-columns: 1fr;
  }
  .benefits-section {
    padding: 20px 10px; /* padding menor em telas pequenas */
  }
}
</style>

