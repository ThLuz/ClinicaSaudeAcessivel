<template>
  <div class="page">
    <header class="navbar">
      <div class="navbar-content">
        <!-- LOGO -->
        <div class="brand">
          <img src="../assets/logo.png" alt="Logo" class="logo-image" />
        </div>

        <!-- LINKS DE NAVEGAÇÃO -->
        <nav :class="['nav-links', { open: isMenuOpen }]">
          <a href="#inicio" :class="{ active: activeLink === 'inicio' }" @click="setActive('inicio')">INÍCIO</a>
          <a href="#servicos" :class="{ active: activeLink === 'servicos' }" @click="setActive('servicos')">SERVIÇOS</a>
          <a href="#planos" :class="{ active: activeLink === 'planos' }" @click="setActive('planos')">PLANOS</a>
          <a href="#about" :class="{ active: activeLink === 'about' }" @click="setActive('about')">SOBRE NÓS</a>
          <a href="#contato" :class="{ active: activeLink === 'contato' }" @click="setActive('contato')">CONTATO</a>
        </nav>

        <!-- BOTÃO MENU MOBILE -->
        <button class="menu-toggle" @click="toggleMenu">
          ☰
        </button>
      </div>
    </header>
  </div>
</template>

<script>
export default {
  name: 'HeroNavbar',
  data() {
    return {
      isMenuOpen: false,
      activeLink: 'inicio', // link inicial ativo
    };
  },
  methods: {
    toggleMenu() {
      this.isMenuOpen = !this.isMenuOpen;
    },
    setActive(link) {
      this.activeLink = link;
      this.isMenuOpen = false; // fecha menu mobile
    },
    onScroll() {
      const sections = ['inicio', 'servicos', 'planos', 'empresa1', 'empresa2', 'contato'];
      const scrollPos = window.scrollY + 80; // 80px = altura navbar + margem de segurança

      for (let i = sections.length - 1; i >= 0; i--) {
        const section = document.getElementById(sections[i]);
        if (section && scrollPos >= section.offsetTop) {
          this.activeLink = sections[i];
          break;
        }
      }
    }

  },
  mounted() {
    window.addEventListener('scroll', this.onScroll);
  },
  beforeUnmount() {
    window.removeEventListener('scroll', this.onScroll);
  }
}
</script>

<style scoped>
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

.page {
  font-family: 'Inter', 'Segoe UI', Roboto, sans-serif;
}

/* NAVBAR BRANCA */
.navbar {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  background: #ffffff;
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.06);
  z-index: 10;
}

/* CONTEÚDO CENTRALIZADO */
.navbar-content {
  max-width: 1200px;
  margin: 0 auto;
  height: 64px;
  display: flex;
  align-items: center;
  justify-content: center;
  position: relative;
  padding: 0 24px;
}

/* LOGO À ESQUERDA */
.brand {
  position: absolute;
  left: 24px;
  display: flex;
  align-items: center;
}

.logo-image {
  width: 60px;
  height: auto;
  object-fit: contain;
  filter: drop-shadow(0 1px 2px rgba(0, 0, 0, 0.1));
}

/* LINKS CENTRALIZADOS */
.nav-links {
  position: absolute;
  left: 50%;
  transform: translateX(-50%);
  display: flex;
  gap: 28px;
}

.nav-links a {
  text-decoration: none;
  color: #333;
  font-weight: 500;
  font-size: 15px;
  padding: 6px 10px;
  white-space: nowrap;
  border-radius: 4px;
  transition: background-color 0.25s ease, color 0.25s ease;
}

/* HOVER */
.nav-links a:hover {
  background-color: #f0f0f0;
  color: #000;
}

/* LINK ATIVO */
.nav-links a.active {
  color: #ff6b00; /* laranja */
  font-weight: 600;
}

/* BOTÃO MENU (MOBILE) */
.menu-toggle {
  position: absolute;
  right: 24px;
  background: none;
  border: none;
  font-size: 32px;
  cursor: pointer;
  color: #333;
  display: none;
}

/* RESPONSIVO */
@media (max-width: 768px) {
  .menu-toggle {
    display: block;
  }

  .nav-links {
    position: absolute;
    top: 72px;
    right: 20px;
    left: auto;
    transform: none;
    flex-direction: column;
    background: #ffffff;
    border-radius: 12px;
    box-shadow: 0 8px 20px rgba(0, 0, 0, 0.12);
    padding: 16px 20px;
    display: none;
    animation: fadeIn 0.3s ease;
  }

  .nav-links.open {
    display: flex;
  }

  .nav-links a {
    color: #333;
    padding: 10px 0;
    font-size: 16px;
  }

  .nav-links a:hover {
    background-color: #f5f5f5;
    color: #000;
  }
}

/* Animação suave menu mobile */
@keyframes fadeIn {
  from {
    opacity: 0;
    transform: translateY(-5px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}
</style>
