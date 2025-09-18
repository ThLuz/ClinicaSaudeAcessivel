<template> 
  <section id="planos" class="planos-section">
    <div class="planos-header">
      <div class="badge-title">
        PLANOS QUE CABEM NO SEU ORÇAMENTO
      </div>
    </div>
    <div class="planos-cards">
      <!-- Plano Vital -->
      <div class="plano-card vital">
        <img src="../assets/item1.png" alt="Vital" />
        <h4 class="plano-title vital">VITAL</h4>
        <p class="plano-price">R$ 19,90 <span>/mês</span></p>
        <ul class="plano-items vital">
          <li class="yes">Consultas com clínico geral por R$29,90</li>
          <li class="yes">Especialidades a partir de R$ 59,90</li>
          <li class="yes">Retorno gratuito com clínico geral dentro de 30 dias</li>
          <li class="no">Inclusão de até 4 dependentes sem custo</li>
        </ul>
        <button class="btn vital">ASSINAR PLANO</button>
      </div>

      <!-- Plano Vital Plus -->
      <div class="plano-card plus">
        <img src="../assets/item2.png" alt="Vital Plus" />
        <h4 class="plano-title plus">VITAL PLUS</h4>
        <p class="plano-price">R$ 49,90 <span>/mês</span></p>
        <ul class="plano-items plus">
          <li class="yes">Consultas com clínico geral por R$29,90</li>
          <li class="yes">Especialidades a partir de R$ 59,90</li>
          <li class="yes">Retorno gratuito com clínico geral dentro de 30 dias</li>
          <li class="yes">Inclusão de até 4 dependentes sem custo</li>
        </ul>
        <button class="btn plus">ASSINAR PLANO</button>
      </div>

      <!-- Plano Vital Premium -->
      <div class="plano-card premium popular">
        <div class="popular-badge">MAIS POPULAR</div>
        <img src="../assets/item3.png" alt="Vital Premium" />
        <h4 class="plano-title premium">VITAL PREMIUM</h4>
        <p class="plano-price">R$ 79,90 <span>/mês</span></p>
        <ul class="plano-items popular">
          <li class="yes">Consultas com clínico geral por R$29,90</li>
          <li class="yes">Especialidades a partir de R$ 59,90</li>
          <li class="yes">Retorno gratuito com clínico geral dentro de 30 dias</li>
          <li class="yes">Inclusão de até 4 dependentes sem custo</li>
        </ul>
        <button class="btn popular">ASSINAR PLANO</button>
      </div>
    </div>
  </section>
</template>

<script setup>
// Sem lógica dinâmica por enquanto
</script>

<style scoped>
.planos-section {
  padding: 60px 20px;
  background-color: #fce2d6; /* fundo claro */
  font-family: 'Montserrat', sans-serif;
  text-align: center;
}

.planos-header h1 {
  margin-bottom: 10px;
}


.planos-cards {
  display: flex;
  justify-content: center;
  gap: 20px;
  flex-wrap: wrap;
}

.plano-card {
  background-color: #fff;
  border-radius: 20px;
  padding: 25px 20px;
  width: 280px;
  position: relative;
  display: flex;
  flex-direction: column;
  align-items: center;
  transition: transform 0.3s ease, box-shadow 0.3s ease;
  box-shadow: 0 8px 25px rgba(0,0,0,0.15);
}

.plano-card:hover {
  transform: translateY(-5px);
}

.badge-title {
  position: relative;
  display: inline-block;
  background-color: #ff7f32; /* Rosa vibrante */
  color: white;
  font-weight: 700;
  font-size: 24px;
  padding: 12px 24px 12px 36px; /* espaço à esquerda */
  border-radius: 6px;
  text-align: center;
  margin: 0 auto;
  margin-bottom: 50px;
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
  border-right: 18px solid #ff7f32;
  transform: translateX(-80%);
  margin-top: 12px;
}


/* Sombra colorida por tipo de plano - versão mais leve */
.plano-card.vital {
  box-shadow: 0 6px 15px rgba(76, 175, 80, 0.2);
}
.plano-card.plus {
  box-shadow: 0 6px 15px rgba(33, 150, 243, 0.2);
}
.plano-card.premium {
  box-shadow: 0 6px 15px rgba(255, 127, 50, 0.2);
}

.popular .popular-badge {
  position: absolute;
  top: -10px;
  right: -10px;
  background-color: #ff7f32;
  color: #fff;
  font-size: 14px;
  padding: 5px 10px;
  border-radius: 12px;
  font-weight: 600;
}

.plano-card img {
  width: 50%;      
  height: auto;
  margin-bottom: 0px;
  border-radius: 12px;
}

.plano-title {
  font-size: 30px;
  font-weight: 600;
  margin-bottom: 0px;
}

/* Cores do título combinando com a sombra */
.plano-title.vital { color: #0A9E6C; }
.plano-title.plus { color: #1388E5; }
.plano-title.premium { color: #F47521; }

.btn.vital { background-color: #0A9E6C; }
.btn.plus { background-color: #1388E5; }
.btn.popular { background-color: #F47521; }

.plano-price {
  font-size: 24px;
  font-weight: 700;
  margin-bottom: 15px;
  color: #333;
}

.plano-price span {
  font-size: 14px;
  font-weight: 400;
  color: #6b5e57;
}

.plano-items {
  text-align: left;
  padding-left: 0;
  list-style: none;
  margin-bottom: 20px;
  width: 100%;
}

.plano-items li {
  margin-bottom: 8px;
  font-size: 14px;
  color: #555;
  position: relative;
  padding-left: 20px;
}

.plano-items li::before {
  content: "✔";
  position: absolute;
  left: 0;
  top: 0;
}

.plano-items.vital li::before { color: #0A9E6C; }
.plano-items.plus li::before{ color: #1388E5; }
.plano-items.popular li::before { color: #F47521; }

.btn {
  background-color: #ff7f32;
  color: #fff;
  font-weight: 600;
  border: none;
  border-radius: 12px;
  padding: 10px 20px;
  cursor: pointer;
  transition: background-color 0.3s ease;
  width: 95%;
}

.btn.vital:hover {
  background-color: #0c8a60;
}
.btn.plus:hover {
  background-color: #0a7dc9;
}
.btn.popular:hover {
  background-color: #e06a1b;
}

/* Mobile */
@media (max-width: 768px) {
  .planos-cards {
    flex-direction: column;
    align-items: center;
  }

  .plano-card {
    width: 90%;
    max-width: 350px;
  }
}
</style>
