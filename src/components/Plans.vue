<template>
  <section id="plans" class="planos-section">
    <div class="planos-header">
      <div class="badge-title">
        PLANOS ODONTOLÓGICOS
      </div>
    </div>

    <div class="planos-cards">
      <div class="plano-card vital">
        <img src="../assets/item1.png" alt="Vital" />
        <h4 class="plano-title vital">ORTO VITAL</h4>

        <div class="plano-values">
          <div class="value-box">
            <span class="label">Adesão</span>
            <strong>R$ 50,00</strong>
          </div>
          <div class="value-box destaque vital">
            <span class="label">Mensalidade</span>
            <strong>R$ 110,00 <span>/mês</span></strong>
          </div>
        </div>

        <ul class="plano-items vital">
          <li>Instalação do aparelho</li>
          <li>01 manutenção mensal</li>
          <li>Remoção e limpeza ao fim do tratamento</li>
          <li>Procedimentos clínicos: 10% de desconto</li>
          <li>Colagem de brackets de R$10,00 por R$5,00</li>
        </ul>

        <button class="btn vital"  @click="assinarPlano('ORTO VITAL')">ASSINAR PLANO</button>
      </div>

      <div class="plano-card plus">
        <img src="../assets/item3.png" alt="Vital Plus" />
        <h4 class="plano-title plus">ORTO VITAL PREMIUM</h4>

        <div class="plano-values">
          <div class="value-box">
            <span class="label">Adesão</span>
            <strong>R$ 50,00</strong>
          </div>
          <div class="value-box destaque plus">
            <span class="label">Mensalidade</span>
            <strong>R$ 140,00 <span>/mês</span></strong>
          </div>
        </div>

        <ul class="plano-items plus">
          <li>Instalação, remoção e limpeza ao fim do tratamento inclusos (gratuitos)</li>
          <li>Documentação inclusa</li>
          <li>01 manutenção mensal</li>
          <li>Todos os procedimentos clínicos com 20% de desconto</li>
          <li>Colagem de brackets sem custo adicional</li>
          <li>Clareamento caseiro ao fim do tratamento</li>
        </ul>

        <button class="btn plus"  @click="assinarPlano('ORTO VITAL PREMIUM')">ASSINAR PLANO</button>
      </div>
    </div>
  </section>
</template>

<script setup>
const whatsappNumber = '5511920744424';

function assinarPlano(plano) {
  const message = `Olá, gostaria de mais informações sobre o plano ${plano}.`;
  const url = `https://wa.me/${whatsappNumber}?text=${encodeURIComponent(message)}`;
  window.open(url, '_blank');
}
</script>


<style scoped>
.planos-section {
  padding: 30px 10px;
  background-color: #fce2d6;
  font-family: 'Montserrat', sans-serif;
  text-align: center;
}

/* HEADER */
.badge-title {
  background-color: #ff7f32;
  color: #fff;
  font-weight: 700;
  font-size: 26px;
  padding: 10px 22px;
  border-radius: 8px;
  margin-bottom: 35px;
  display: inline-block;
}

.planos-cards {
  display: flex;
  justify-content: center;
  gap: 32px;
  flex-wrap: wrap;
}

.plano-card {
  background-color: #fff;
  border-radius: 20px;
  padding: 18px 16px; 
  width: 350px;       
  display: flex;
  flex-direction: column;
  align-items: center;
  box-shadow: 0 8px 24px rgba(0,0,0,0.14);
  transition: transform 0.3s ease;
}

.plano-card:hover {
  transform: translateY(-5px);
}

.plano-card.vital {
  box-shadow: 0 8px 20px rgba(10, 158, 108, 0.22);
}

.plano-card.plus {
  box-shadow: 0 8px 20px rgba(245, 121, 20, 0.22);
}

.plano-card img {
  width: 52%;
  margin-bottom: 4px;
}

.plano-title {
  font-size: 26px; 
  font-weight: 700;
  margin-bottom: 6px;
}

.plano-title.vital { color: #0A9E6C; }
.plano-title.plus  { color: #ff7f32; }

.plano-values {
  display: flex;
  gap: 12px;
  margin-bottom: 6px;
}

.value-box {
  border: 1px solid #eee;
  border-radius: 12px;
  padding: 10px 14px;
  min-width: 140px;
  display: flex;              
  flex-direction: column;     
  align-items: center;       
  text-align: center;
  color: #777;
}


.value-box .label {
  font-size: 12px;
  color: #777;
  margin-bottom: 4px;
  display: block;            
}


.value-box strong {
  font-size: 18px;
}

.value-box strong span {
  font-size: 12px;
}

.value-box.destaque.vital { border-color: #0A9E6C; }
.value-box.destaque.plus  { border-color: #ff7f32; }

.plano-items {
  list-style: none;
  padding: 0;
  margin-bottom: 20px;
  width: 100%;
  text-align: left;
  color: #6b5e57;
}

.plano-items li {
  font-size: 13px; 
  margin-bottom: 8px;
  padding-left: 20px;
  position: relative;
}

.plano-items li::before {
  content: "✔";
  position: absolute;
  left: 0;
  top: 0;
}

.plano-items.vital li::before { color: #0A9E6C; }
.plano-items.plus li::before  { color: #ff7f32; }

.plano-items li:empty::before {
  content: none;
}

.plano-items li:empty {
  min-height: 20px;
}

.btn {
  width: 100%;
  padding: 10px;
  border-radius: 12px;
  border: none;
  color: #fff;
  font-weight: 600;
  font-size: 14px;
  cursor: pointer;
  margin-top: auto;
}

.btn.vital { background-color: #0A9E6C; }
.btn.plus  { background-color: #ff7f32; }

.btn.vital:hover { background-color: #0c8a60; }
.btn.plus:hover  { background-color: #fa6f19; }

.photo-1 {
  grid-column: 2;
  grid-row: 1;
  height: 120px;
  background-image: url('@/assets/about1.jpeg');
}

.photo-2 {
  grid-column: 1;
  grid-row: 2;
  background-image: url('@/assets/about2.jpeg');
}

.photo-3 {
  grid-column: 2;
  grid-row: 2;
  height: 150px;
  background-image: url('@/assets/about3.jpeg');
}

.photo-4 {
  grid-column: 3;
  grid-row: 2;
  background-image: url('@/assets/about4.jpeg');
}

.photo-5 {
  grid-column: 1;
  grid-row: 3;
  height: 120px;
  background-image: url('@/assets/about5.jpg');
}

.photo-6 {
  grid-column: 3;
  grid-row: 3;
  height: 120px;
  background-image: url('@/assets/about6.jpg');
}

@media (max-width: 912px) {
  .plano-values {
    flex-direction: row;
    justify-content: center;
    gap: 8px;
  }

  .badge-title {
    font-size: 20px;
  }

  .value-box {
    min-width: 100px;
    padding: 6px 8px;
    font-size: 12px;
  }

  .plano-card {
    width: 80%;
    padding: 16px;
  }

  .plano-title {
    font-size: 20px;
  }

  .plano-items li {
    font-size: 12px;
    margin-bottom: 6px;
  }

  .btn {
    font-size: 13px;
    padding: 8px;
  }

  .about-photos {
    display: grid !important;
    grid-template-columns: repeat(2, 1fr);
    gap: 16px;
    padding: 20px;
  }

  .about-photos .photo {
    width: 100%;
    min-height: 150px;
    aspect-ratio: 1 / 1;
  }
  
  .planos-cards {
    display: flex;
    justify-content: center;
    gap: 32px;
    flex-wrap: nowrap;
  }

  .plano-card {
    padding: 18px 16px; 
    width: 320px;       
  }
}

@media (max-width: 480px) {
  .planos-cards {
    display: flex;
    justify-content: center;
    gap: 32px;
    flex-wrap: wrap;
  }
}

</style>
