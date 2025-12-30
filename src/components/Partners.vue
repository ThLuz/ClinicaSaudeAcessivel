<template>
  <section class="parceiros-section">
    <div class="parceiros-container">
      <!-- Logo do MeuClube -->
      <img src="../assets/meuclube.png" alt="Meu Clube Online" class="logo-meuclube" />

      <p class="descricao">
        + de 100 Parceiros com descontos em serviços, benefícios e vantagens.
      </p>

      <div class="logos">
        <img src="../assets/amazon.png" alt="amazon" />
        <img src="../assets/riachuelo.png" alt="riachuelo" />
        <img src="../assets/duolingo.png" alt="duolingo" />
        <img src="../assets/magalu.png" alt="magalu" />
      </div>
    </div>
  </section>
</template>

<script setup>
</script>

<style scoped>
.parceiros-section {
  background: linear-gradient(90deg, #0753b4 0%, #1388E5 100%);
  padding: 25px 15px;
  display: flex;
  justify-content: center;
  font-family: 'Montserrat', sans-serif;
  color: #fff;
  text-align: center;
}

.parceiros-container {
  max-width: 700px;
}

.sub-title {
  font-size: 14px;
  font-weight: 500;
  margin-bottom: 6px;
  letter-spacing: 0.5px;
}

.logo-meuclube {
  max-width: 250px; /* controla o tamanho do logo */
  margin: 0 auto 15px;
  display: block;
}

.descricao {
  font-size: 20px;
  font-weight: 400;
  line-height: 1.5;
  margin-bottom: 20px;
}

.logos {
  display: flex;
  justify-content: center;
  flex-wrap: wrap;
  gap: 18px;
  margin-bottom: 12px;
}

.logos img {
  max-height: 28px;
  object-fit: contain;
}

.mais {
  font-size: 13px;
  margin-top: 5px;
}
</style>
