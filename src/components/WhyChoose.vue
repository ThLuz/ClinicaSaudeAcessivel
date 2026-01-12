<template>
  <section class="clinic-section">
    <div class="container">

      <!-- COLUNA TEXTO -->
      <div class="text-column">
        <h2>CONHEÇA NOSSA CLÍNICA EM SÃO PAULO</h2>
        <p>
          Na nossa clínica, unimos excelência em saúde e estética para oferecer a melhor experiência aos nossos pacientes.
          Realizamos tratamentos odontológicos, psicológicos, fisioterapêuticos, nutricionais e estéticos corporais e faciais 
          com profissionais especializados. Nosso espaço foi projetado para proporcionar conforto, bem estar e atendimento personalizado, 
          garantindo que cada experiência seja única.
        </p>

        <button class="btn-schedule" @click="abrirWhatsApp">AGENDE SUA AVALIAÇÃO</button>
      </div>

      <!-- COLUNA IMAGEM -->
      <div class="image-column">

        <div class="image-wrapper">
          <img src="../assets/about3.jpeg" alt="Clínica" />

          <!-- CARDS SOBRE A IMAGEM -->
          <div class="info-cards">

            <div class="card card-patients">
              <div class="card-title">Pacientes</div>
              <div class="card-number">+8 mil</div>
              <div class="card-subtitle">Atendidos</div>
            </div>

            <div class="card card-equipment">
              <i class="fas fa-microscope card-icon"></i>
              <div class="card-title">Equipamentos</div>
              <div class="card-subtitle">de última geração</div>
            </div>

            <div class="card card-location">
              <i class="fas fa-map-marker-alt card-icon"></i>
              <div class="card-subtitle">Pertinho de você</div>
            </div>

          </div>
        </div>

      </div>

    </div>
  </section>
</template>

<script setup>
const whatsappNumber = '5511920744424';

function abrirWhatsApp() {
  const message = "Oi! Estou curioso para saber mais sobre a clínica 😃"; // mensagem pronta
  const url = `https://wa.me/${whatsappNumber}?text=${encodeURIComponent(message)}`;
  window.open(url, "_blank"); // abre em nova aba
}
</script>

<style scoped>
/* ===================== */
/* SEÇÃO */
/* ===================== */
.clinic-section {
  background-color: #ffffff;
  padding: 80px 20px;
  font-family: 'Montserrat', sans-serif;
  overflow-x: hidden;
}

/* ===================== */
/* CONTAINER */
/* ===================== */
.container {
  max-width: 1200px;
  margin: 0 auto;
  display: flex;
  gap: 40px;
  align-items: flex-start;
  flex-wrap: wrap;
}

/* ===================== */
/* COLUNAS */
/* ===================== */
.text-column {
  flex: 1 1 500px;
}

.image-column {
  flex: 1 1 400px;
}

/* ===================== */
/* IMAGEM */
/* ===================== */
.image-wrapper {
  position: relative;
}

.image-wrapper img {
  width: 100%;
  border-radius: 16px;
  object-fit: cover;
  display: block;
}

/* ===================== */
/* TEXTO */
/* ===================== */
h2 {
  font-size: 34px;
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

/* ===================== */
/* BOTÃO */
/* ===================== */
.btn-schedule {
  padding: 12px 25px;
  background-color: #f8944c;
  color: #fff;
  font-weight: 600;
  border: none;
  border-radius: 12px;
  cursor: pointer;
  transition: background-color 0.3s ease;
}

.btn-schedule:hover {
  background-color: #f18a28;
}

/* ===================== */
/* CARDS SOBRE A IMAGEM */
/* ===================== */
.info-cards {
  position: absolute;
  bottom: 8px;
  right: 8px;

  display: flex;
  gap: 16px;
  pointer-events: none;
}

/* ===================== */
/* CARD BASE */
/* ===================== */
.card {
  width: 90px;
  height: 80px;
  padding: 10px;
  border-radius: 12px;
  color: #ffffff;

  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  gap: 2px;

  text-align: center;
}

.card-title {
  font-size: 11px;
  opacity: 0.85;
}

.card-subtitle {
  font-size: 11px;
  opacity: 0.85;
}

.card-icon,
.card-number {
  font-size: 18px;
  font-weight: 700;
}

/* ===================== */
/* CORES */
/* ===================== */
.card-patients {
  background-color: #f8944c;
}

.card-equipment {
  background-color: #50a1e2;
}

.card-location {
  background-color: #3cb371;
}

/* ===================== */
/* MOBILE */
/* ===================== */
@media (max-width: 900px) {

  .clinic-section {
    padding-top: 30px;   
    padding-bottom: 40px;
  }

  h2 {
    margin-top: 0;
    margin-bottom: 25px;
    font-size: 24px;
  }

  .plano-card {
    width: 92%;
    padding: 12px 12px 8px; /* ⬅️ menos branco embaixo */
  }

  .plano-card img {
    width: 65%;            /* ⬅️ imagem maior */
    margin-bottom: 6px;    /* ⬅️ menos espaço */
  }

  .plano-title {
    font-size: 18px;
    margin-bottom: 4px;
  }

  .value-box {
    padding: 6px 8px;
    min-width: 95px;
    margin-bottom: 6px;
  }

  .value-box strong {
    font-size: 15px;
  }

  .plano-items {
    margin-bottom: 8px;    /* ⬅️ remove espaço excessivo */
  }

  .plano-items li {
    font-size: 11px;
    margin-bottom: 4px;
  }

  .btn {
    padding: 8px;
    font-size: 12px;
  }
}

</style>
