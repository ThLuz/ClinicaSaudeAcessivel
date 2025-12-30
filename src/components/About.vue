<template>
  <section id="about" class="about-section">
    <div class="about-container">
      
      <!-- TEXTO (FUNDO BRANCO COM LOGO) -->
      <div class="about-text">
        <h2>
          Clínica <span>Saúde Acessível</span>
        </h2>

        <p>
          Na Clínica Saúde Acessível, acreditamos que saúde de qualidade deve ser
          acessível e completa. Por isso, reunimos em um só espaço atendimentos
          médicos, odontológicos e exames laboratoriais, oferecendo praticidade
          e cuidado integral para nossos pacientes.
        </p>

        <p>
          Nossa missão é proporcionar um atendimento humanizado, seguro e
          transparente, com profissionais qualificados e estrutura moderna.
          Mais do que tratar doenças, queremos cuidar de pessoas, promovendo
          saúde, bem-estar e confiança em cada consulta.
        </p>

        <p class="highlight">
          Seja bem-vindo à Clínica Saúde Acessível:
          <strong>a sua saúde em boas mãos 🧡</strong>
        </p>
      </div>

      <!-- FOTOS -->
      <div class="about-photos">
        <div class="photo" :style="{ backgroundImage: `url(${about1})` }"></div>
        <div class="photo" :style="{ backgroundImage: `url(${about2})` }"></div>
        <div class="photo" :style="{ backgroundImage: `url(${about3})` }"></div>

        <div class="photo" :style="{ backgroundImage: `url(${about4})` }"></div>
        <div class="photo" :style="{ backgroundImage: `url(${about5})` }"></div>
        <div class="photo" :style="{ backgroundImage: `url(${about6})` }"></div>

        <div class="photo" :style="{ backgroundImage: `url(${about7})` }"></div>
        <div class="photo" :style="{ backgroundImage: `url(${about8})` }"></div>
        <div class="photo" :style="{ backgroundImage: `url(${about9})` }"></div>
      </div>

    </div>
  </section>
</template>

<script setup>
import about1 from '../assets/about1.jpeg'
import about2 from '../assets/about2.jpeg'
import about3 from '../assets/about3.jpeg'
import about4 from '../assets/about4.jpeg'
import about5 from '../assets/about5.jpeg'
import about6 from '../assets/about6.jpeg'
import about7 from '../assets/about7.jpg'
import about8 from '../assets/about8.jpeg'
import about9 from '../assets/about9.jpeg'
</script>

<style scoped>
.about-section {
  background-color: #d8d8d8;
  padding: 30px;
  font-family: 'Montserrat', sans-serif;
}

/* CONTAINER */
.about-container {
  max-width: 1200px;
  margin: 0 auto;
  display: grid;
  grid-template-columns: 1fr 1fr;
  border-radius: 24px;
  overflow: hidden;
  box-shadow: 0 15px 40px rgba(0,0,0,0.15);
}

/* TEXTO COM LOGO DE FUNDO */
.about-text {
  background-color: #ffffff;
  padding: 60px 50px;
  color: #6b5e57;

  /* LOGO DE FUNDO */
  background-image: url('../assets/logo.png');
  background-repeat: no-repeat;
  background-position: center;
  background-size: 300px;
  position: relative;
}

/* camada para deixar a logo bem fraquinha */
.about-text::before {
  content: '';
  position: absolute;
  inset: 0;
  background-color: rgba(255, 255, 255, 0.88);
}

.about-text > * {
  position: relative;
  z-index: 1;
}

.about-text h2 {
  font-size: 36px;
  font-weight: 700;
  margin-bottom: 24px;
  color: #333;
}

.about-text h2 span {
  color: #ff7f32;
}

.about-text p {
  font-size: 16px;
  line-height: 1.7;
  margin-bottom: 18px;
}

.about-text .highlight {
  margin-top: 24px;
  font-size: 17px;
}

/* FOTOS */
.about-photos {
  background-color: #eef6fb;
  padding: 40px;
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 16px;
}

.photo {
  aspect-ratio: 1 / 1;
  border-radius: 18px;
  background-size: cover;
  background-position: center;
  box-shadow: 0 10px 25px rgba(0,0,0,0.15);
}

/* MOBILE */
@media (max-width: 900px) {
  .about-container {
    grid-template-columns: 1fr;
  }

  .about-text {
    text-align: center;
    padding: 50px 30px;
    background-size: 220px;
  }

  .about-photos {
    padding: 30px;
  }
}
</style>
