<template>
  <div class="page">
    <header class="navbar">
      <div class="brand">
        <img src="../assets/logo.png" alt="Logo" class="logo-image" />
      </div>

      <!-- Botão de menu hamburguer -->
      <button class="menu-toggle" @click="toggleMenu">
        ☰
      </button>

      <!-- Menu de navegação -->
      <nav :class="['nav-links', { open: isMenuOpen }]">
        <a href="#inicio">INÍCIO</a>
        <a href="#solucoes">SERVIÇOS</a>
        <a href="#jornada">PLANOS</a>
        <a href="#blog">PLANOS EMPRESARIAIS</a>
        <a href="#contato">CONTATO</a>
      </nav>
    </header>
  </div>
</template>

<script>
export default {
  name: 'HeroNavbarGradient',
  data() {
    return {
      isMenuOpen: false,
    };
  },
  methods: {
    toggleMenu() {
      this.isMenuOpen = !this.isMenuOpen;
    }
  }
}
</script>

<style scoped>
* {
  box-sizing: border-box;
}

.page {
  font-family: Inter, "Segoe UI", Roboto, sans-serif;
}

.navbar {
  position: fixed;
  top: 20px;
  left: 50%;
  transform: translateX(-50%);
  width: calc(100% - 40px);
  max-width: 1200px;
  height: 64px;
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 12px 24px;
  background: #fff;
  border-radius: 999px;
  box-shadow: 0 14px 30px rgba(15, 15, 15, 0.12);
  z-index: 10;
}

.brand {
  display: flex;
  align-items: center;
  justify-content: center;
  pointer-events: none; /* impede clique na logo se ela sobrepor o botão ou menu */
}

.logo-image {
  width: 65px;
  height: auto;
  object-fit: contain;
}

.menu-toggle {
  display: none;
  background: none;
  border: none;
  font-size: 40px;
  cursor: pointer;
  color: #000;

}

.nav-links {
  display: flex;
  gap: 24px;
}

.nav-links a {
  text-decoration: none;
  color: #333;
  font-weight: 500;
  padding: 6px 8px;
}

.nav-links a:hover {
  color: #000;
}

@media (max-width: 768px) {
  .menu-toggle {
    display: block;
  }

  .nav-links {
    position: absolute;
    top: 72px;
    right: 20px;
    flex-direction: column;
    background: white;
    padding: 16px 24px;
    border-radius: 12px;
    box-shadow: 0 8px 20px rgba(0, 0, 0, 0.1);
    display: none;
  }

  .nav-links.open {
    display: flex;
  }
}
</style>
