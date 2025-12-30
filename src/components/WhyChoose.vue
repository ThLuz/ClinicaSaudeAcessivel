<template>
  <section class="clinic-section">
    <div class="container">

      <!-- COLUNA TEXTO -->
      <div class="text-column">
        <h2>Conheça Nossa Clínica em São Paulo</h2>
        <p>
          Na nossa clínica, unimos excelência em odontologia e estética para oferecer a melhor experiência aos nossos pacientes.
          Realizamos tratamentos odontológicos completos, desde prevenção e restaurações até estética dental.  
          Em estética, contamos com depilação a laser, remoção de tatuagens, aplicação de botox, preenchimentos faciais e outros procedimentos
          modernos, com técnicas seguras e profissionais especializados.  
          Nosso espaço foi projetado para proporcionar conforto, bem-estar e atendimento personalizado, garantindo que cada visita seja única.
        </p>

        <!-- BOTÃO AGENDAR AVALIAÇÃO -->
        <button class="btn-schedule">Agende sua Avaliação</button>
      </div>

      <!-- COLUNA IMAGEM -->
      <div class="image-column">
        <img src="../assets/about3.jpeg" alt="Clínica" />

        <!-- CARDS SOBRE A IMAGEM -->
        <div class="info-cards">
          <div class="card card-patients">
            <div class="card-title">Pacientes</div>
            <div class="card-number">+8 mil</div>
            <div class="card-subtitle">Atendidos</div>
          </div>

          <div class="card card-professionals">
            <div class="card-title">Profissionais</div>
            <div class="card-number">15</div>
            <div class="card-subtitle">Especialistas</div>
          </div>
        </div>
      </div>

    </div>
  </section>
</template>

<script setup>
/* section clínica */
</script>

<style scoped>
/* SEÇÃO */
.clinic-section {
  background-color: #ffffff;
  padding: 80px 20px;
  font-family: 'Montserrat', sans-serif;
}

/* CONTAINER */
.container {
  max-width: 1200px;
  margin: 0 auto;
  display: flex;
  gap: 40px;
  align-items: flex-start;
  flex-wrap: wrap;
}

/* COLUNAS */
.text-column {
  flex: 1 1 500px;
}

.image-column {
  flex: 1 1 400px;
  position: relative;
}

.image-column img {
  width: 100%;
  border-radius: 16px;
  object-fit: cover;
}

/* TÍTULO E TEXTO */
h2 {
  font-size: 42px;
  font-weight: 800;
  margin-bottom: 25px;
  color: #2b2b2b;
  line-height: 1.2;
  font-family: 'Poppins', sans-serif;
}

p {
  font-size: 16px;
  line-height: 1.8;
  color: #6b5e57;
  margin-bottom: 30px;
}

/* BOTÃO AGENDAR */
.btn-schedule {
  display: inline-block;
  padding: 12px 25px;
  background-color: #b35900; /* laranja escuro */
  color: #fff;
  font-weight: 600;
  border: none;
  border-radius: 40px;
  cursor: pointer;
  transition: background-color 0.3s ease;
}

.btn-schedule:hover {
  background-color: #ff7a00;
}

/* CARDS SOBRE A IMAGEM */
.info-cards {
  position: absolute;
  top: 93%;
  left: 5%;
  width: 100%;
  display: flex;
  gap: 20px;
  transform: translateY(-50%);
}

/* ESTILO BASE DOS CARDS */
.card {
  padding: 20px;
  border-radius: 16px;
  text-align: center;
  min-width: 150px;
  color: #ffffff;
}

.card-title {
  font-size: 14px;
  opacity: 0.8;
  margin-bottom: 8px;
}

.card-number {
  font-size: 24px;
  font-weight: 700;
  margin-bottom: 4px;
}

.card-subtitle {
  font-size: 14px;
  opacity: 0.8;
}

/* PRIMEIRO CARD - PACIENTES */
.card-patients {
  background-color: #ff905d; /* laranja clarinho */
  position: absolute;
  left: -50px; /* metade para fora da imagem */
  top: 50%;
  transform: translateY(-50%);
  z-index: 2;
}

/* SEGUNDO CARD - PROFISSIONAIS */
.card-professionals {
  background-color: #50a1e2;
  position: relative;
  z-index: 1;
  margin-left: 120px;
}

/* MOBILE */
@media (max-width: 900px) {
  .container {
    flex-direction: column;
    gap: 40px;
  }

  h2 {
    font-size: 32px;
  }

  .info-cards {
    position: static;
    flex-direction: row;
    justify-content: flex-start;
    margin-top: 20px;
    transform: none;
  }

  .card-patients {
    position: static;
    transform: none;
    left: auto;
    top: auto;
    margin-right: 0;
  }
}
</style>
