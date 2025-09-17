<template> 
  <section class="planos-section">
    <div class="planos-header">
      <h3>Planos que encaixam no orçamento</h3>
      <h2>Escolha o seu</h2>
    </div>

    <div class="planos-cards">
      <!-- Plano Vital -->
      <div class="plano-card vital">
        <img src="../assets/item1.png" alt="Vital" />
        <h4 class="plano-title vital">Vital</h4>
        <p class="plano-price">R$ 19,90 <span>/mês</span></p>
        <ul class="plano-items">
          <li>Consultas com clínico geral por R$29,90</li>
          <li>Retorno gratuito com clínico geral dentro de 30 dias</li>
        </ul>
        <button class="btn">Escolher</button>
      </div>

      <!-- Plano Vital Plus -->
      <div class="plano-card plus">
        <img src="../assets/imagem2.jpg" alt="Vital Plus" />
        <h4 class="plano-title plus">Vital Plus</h4>
        <p class="plano-price">R$ 49,90 <span>/mês</span></p>
        <ul class="plano-items">
          <li>Consultas com clínico geral por R$29,90</li>
          <li>Retorno gratuito com clínico geral dentro de 30 dias</li>
        </ul>
        <button class="btn">Escolher</button>
      </div>

      <!-- Plano Vital Premium -->
      <div class="plano-card premium popular">
        <div class="popular-badge">Mais Popular</div>
        <img src="../assets/imagem3.jpg" alt="Vital Premium" />
        <h4 class="plano-title premium">Vital Premium</h4>
        <p class="plano-price">R$ 79,90 <span>/mês</span></p>
        <ul class="plano-items">
          <li>Consultas com clínico geral por R$29,90</li>
          <li>Retorno gratuito com clínico geral dentro de 30 dias</li>
        </ul>
        <button class="btn">Escolher</button>
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
  background-color: #fbe9e7; /* fundo claro */
  font-family: 'Montserrat', sans-serif;
  text-align: center;
}

.planos-header h3 {
  color: #ff7f32;
  font-size: 22px;
  margin-bottom: 5px;
}

.planos-header h2 {
  font-size: 32px;
  font-weight: 600;
  color: #6b5e57;
  margin-bottom: 40px;
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
  font-size: 12px;
  padding: 5px 10px;
  border-radius: 12px;
  font-weight: 600;
}

.plano-card img {
  width: 50%;      
  height: auto;
  margin-bottom: 15px;
  border-radius: 12px;
}

.plano-title {
  font-size: 30px;
  font-weight: 600;
  margin-bottom: 10px;
}

/* Cores do título combinando com a sombra */
.plano-title.vital { color: #0A9E6C; }
.plano-title.plus { color: rgba(33, 150, 243, 0.8); }
.plano-title.premium { color: rgba(255, 127, 50, 0.8); }

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
  color: #ff7f32;
  position: absolute;
  left: 0;
  top: 0;
}

.btn {
  background-color: #ff7f32;
  color: #fff;
  font-weight: 600;
  border: none;
  border-radius: 12px;
  padding: 10px 20px;
  cursor: pointer;
  transition: background-color 0.3s ease;
}

.btn:hover {
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
