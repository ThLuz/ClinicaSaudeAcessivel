<template>
  <a
    class="whatsapp-button"
    :href="whatsappLink"
    target="_blank"
    rel="noopener noreferrer"
    aria-label="Fale conosco no WhatsApp"
  >
    <svg
      xmlns="http://www.w3.org/2000/svg"
      viewBox="0 0 32 32"
      class="whatsapp-icon"
    >
      <path
        fill="white"
        d="M16.003 2.004a13.99 13.99 0 00-12.09 21.032L2 30l7.14-1.879A13.99 13.99 0 1016.002 2zm0 25.9a11.867 11.867 0 01-6.071-1.662l-.434-.257-4.231 1.113 1.128-4.125-.282-.446a11.9 11.9 0 1110.002 5.377zm6.539-8.486c-.358-.179-2.118-1.043-2.447-1.161-.329-.119-.57-.179-.812.18s-.933 1.161-1.144 1.4c-.21.239-.419.269-.777.09-.358-.18-1.511-.555-2.88-1.772-1.064-.949-1.781-2.122-1.989-2.48-.209-.358-.023-.55.157-.729.162-.162.358-.419.538-.628.179-.21.239-.358.358-.597.12-.239.06-.448-.03-.628-.09-.18-.812-1.956-1.11-2.675-.293-.7-.589-.6-.812-.612l-.693-.012a1.33 1.33 0 00-.96.45c-.33.359-1.26 1.229-1.26 2.993 0 1.764 1.291 3.469 1.47 3.708.18.239 2.537 3.877 6.147 5.433 3.611 1.556 3.611 1.037 4.26.976.652-.06 2.118-.867 2.417-1.705.299-.838.299-1.558.209-1.705-.089-.149-.329-.239-.688-.419z"
      />
    </svg>
  </a>
</template>

<script setup>
const phone = '5511990274243';

const message =
  'Olá, vim pelo site da Clínica Saúde Acessível e gostaria de mais informações.';

const whatsappLink = `https://wa.me/${phone}?text=${encodeURIComponent(message)}`;
</script>

<style scoped>
.whatsapp-button {
  position: fixed;
  bottom: 24px;
  right: 24px;
  width: 60px;
  height: 60px;
  background-color: #25d366;
  border-radius: 50%;
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.25);
  display: flex;
  align-items: center;
  justify-content: center;
  z-index: 999;
  transition: transform 0.3s ease;
}

.whatsapp-button:hover {
  transform: scale(1.1);
}

.whatsapp-icon {
  width: 30px;
  height: 30px;
}
</style>
