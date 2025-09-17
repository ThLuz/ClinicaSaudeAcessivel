<template>
  <section class="contact-section">
    <div class="badge-title">
      SAIBA COMO CHEGAR
    </div>    
    <div class="contact-content">
      <!-- Coluna de informações -->
      <div class="contact-info">
        <!-- Endereço -->
        <div class="info-item">
          <div class="icon-title">
            <i class="fas fa-map-marker-alt"></i>
            <strong>Endereço</strong>
          </div>
          <p>Av. Alexios Jafet, 1196 - Jardim Ipanema (Zona Oeste), São Paulo - SP, 05187-010</p>
        </div>

        <!-- Horário de funcionamento -->
        <div class="info-item">
          <div class="icon-title">
            <i class="fas fa-clock"></i>
            <strong>Horário de funcionamento</strong>
          </div>
          <p>Segunda a sexta: 07:00–19:00<br>
             Sábado: 08:00–14:00<br>
             Domingo: Fechado
          </p>
        </div>

        <!-- Telefone -->
        <div class="info-item">
          <div class="icon-title">
            <i class="fas fa-phone-alt"></i>
            <strong>Telefone</strong>
          </div>
          <p>(11) 92074-4424</p>
        </div>
      </div>

      <!-- Mapa -->
      <div class="contact-map">
        <iframe 
          src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d3657.053924781612!2d-46.70122068448566!3d-23.55076918469125!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x94ce5769a8c1b421%3A0x43a2f8d7f3a6d2a!2sAv.%20Alexios%20Jafet%2C%201196%20-%20Jardim%20Ipanema%2C%20S%C3%A3o%20Paulo%20-%20SP%2C%2005187-010!5e0!3m2!1spt-BR!2sbr!4v1694892160000!5m2!1spt-BR!2sbr"
          width="100%" 
          height="100%" 
          style="border:0;" 
          allowfullscreen="" 
          loading="lazy" 
          referrerpolicy="no-referrer-when-downgrade">
        </iframe>
      </div>
    </div>
  </section>
</template>

<script setup>
// Sem lógica dinâmica
</script>

<style scoped>
@import url("https://cdnjs.cloudflare.com/ajax/libs/font-awesome/5.15.4/css/all.min.css");

.contact-section {
  padding: 60px 20px;
  background-color: #3a3a3a;
  color: #fff;
  font-family: 'Montserrat', sans-serif;
}

.contact-content {
  display: flex;
  justify-content: center;
  gap: 50px;
  max-width: 1000px;
  margin: 0 auto;
  flex-wrap: wrap;
}

.contact-info, .contact-map {
  flex: 1;
  min-width: 400px;
}

.contact-info {
  display: flex;
  flex-direction: column;
  gap: 25px; /* aumento do gap */
  align-items: center;
  text-align: center;
}

.badge-title {
  position: relative;
  display: inline-block;
  background-color: #555; /* Rosa vibrante */
  color: white;
  font-weight: 700;
  font-size: 24px;
  padding: 12px 24px 12px 36px; /* espaço à esquerda */
  border-radius: 2px;
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
  border-right: 18px solid #555;
  transform: translateX(-80%);
  margin-top: 12px;
}

/* Blocos de informação levemente maiores */
.info-item {
  display: flex;
  flex-direction: column;
  gap: 8px; /* maior gap entre elementos */
  font-weight: 600;
  background-color: #555;
  padding: 22px 20px; /* padding maior */
  border-radius: 15px;
  box-shadow: 0 5px 15px rgba(0,0,0,0.2);
  width: 100%;
  max-width: 400px;
  text-align: center;
  transition: transform 0.3s ease, background-color 0.3s ease;
}

.info-item:hover {
  transform: translateY(-2px);
  background-color: #666;
}

.icon-title {
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 8px; /* gap maior entre ícone e título */
}

.icon-title i {
  font-size: 24px; /* ícones um pouco maiores */
  color: #fff;
}

.info-item p {
  font-size: 15px; /* texto um pouco maior */
  margin: 0;
  line-height: 1.4;
}

.contact-map {
  height: 400px;
  border-radius: 20px;
  overflow: hidden;
  box-shadow: 0 10px 30px rgba(0,0,0,0.3);
  padding: 25px;
  background-color: #2a2a2a;
  box-sizing: border-box;
}

/* Mobile */
@media (max-width: 1024px) {
  .contact-content {
    flex-direction: column;
    align-items: center;
  }

  .contact-map, .contact-info {
    width: 90%;
    min-width: unset;
  }

  .contact-map {
    height: 300px;
    padding: 20px;
  }
 
  .contact-section h2 {
    font-size: 25px;
  }
}
</style>
