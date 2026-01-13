<template>
  <footer class="footer">
    <div class="footer-content">
      <span class="footer-text">
        © {{ year }} Clínica Saúde Acessível
      </span>
      <span class="footer-divider">|</span>
      <span class="footer-text">
        Todos os direitos reservados
      </span>
    </div>
  </footer>
</template>

<script setup>
const year = new Date().getFullYear()
</script>

<style scoped>
.footer {
  background-color: #2a2a2a;
  border-top: 1px solid #444;
  padding: 15px 10px;
  font-family: 'Montserrat', sans-serif;
}

.footer-content {
  display: flex;
  justify-content: center;
  align-items: center;
  gap: 8px;
  flex-wrap: wrap;
}

.footer-text {
  color: #ccc;
  font-size: 14px;
  font-weight: 500;
}

.footer-divider {
  color: #555;
  font-size: 14px;
}

@media (max-width: 480px) {
  .footer-divider {
    display: none;
  }

  .footer-content {
    flex-direction: column;
    gap: 4px;
  }
}
</style>
