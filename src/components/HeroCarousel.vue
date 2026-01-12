<template>
  <div class="back">
    <div id="home" class="carousel">
      <div class="carousel-track" :style="{ transform: `translateX(-${currentIndex * 100}%)` }">
        <div class="carousel-slide" v-for="(slide, index) in slides" :key="index">
          <img :src="slide" alt="Slide" />
        </div>
      </div>

      <button class="arrow left" @click="prevSlide" aria-label="Slide anterior">
        <span>&#10094;</span>
      </button>
      <button class="arrow right" @click="nextSlide" aria-label="Próximo slide">
        <span>&#10095;</span>
      </button>

      <div class="dots">
        <span v-for="(slide, index) in slides" :key="index" 
              :class="{ active: index === currentIndex }" 
              @click="currentIndex = index"></span>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue'
import img1 from '../assets/imagem1.jpeg'
import img2 from '../assets/imagem2.jpeg'
import img3 from '../assets/imagem3.jpeg'

const slides = [img1, img2, img3]
const currentIndex = ref(0)

const nextSlide = () => currentIndex.value = (currentIndex.value + 1) % slides.length
const prevSlide = () => currentIndex.value = (currentIndex.value - 1 + slides.length) % slides.length
</script>

<style scoped>
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

.back {
  background-color: #eee;
  box-shadow: 8px 0 20px rgba(0, 0, 0, 0.2),
              -8px 0 20px rgba(0, 0, 0, 0.2);
}

/* ===== CAROUSEL ===== */
.carousel {
  width: 100%;
  overflow: hidden;
  position: relative;
  margin-top: 32px;
}

.carousel-track {
  display: flex;
  transition: transform 0.5s ease-in-out;
}

/* Cada slide ocupa 100% */
.carousel-slide {
  min-width: 100%;
  position: relative;
}

/* Imagem padrão (desktop) */
.carousel-slide img {
  width: 100%;
  height: 600px;
  object-fit: cover;
  display: block;
  filter: brightness(80%);
  transition: transform 0.3s ease, filter 0.3s ease;
}

/* ===== SETAS ===== */
.arrow {
  position: absolute;
  top: 50%;
  transform: translateY(-50%);
  background: rgba(255, 255, 255, 0.4);
  border: none;
  border-radius: 50%;
  width: 55px;
  height: 55px;
  display: flex;
  align-items: center;
  justify-content: center;
  cursor: pointer;
  z-index: 2;
}

.arrow span {
  font-size: 28px;
  color: #333;
}

.arrow.left { left: 12px; }
.arrow.right { right: 12px; }

/* ===== DOTS ===== */
.dots {
  position: absolute;
  bottom: 16px;
  left: 50%;
  transform: translateX(-50%);
  display: flex;
  gap: 12px;
}

.dots span {
  width: 14px;
  height: 14px;
  background: rgba(255,255,255,0.8);
  border-radius: 50%;
  cursor: pointer;
}

.dots span.active {
  background: #ff7f32;
  transform: scale(1.4);
}

/* ===================== */
/* 📱 MOBILE AJUSTADO */
/* ===================== */
@media (max-width: 912px) {

  .carousel-slide {
    height: 450px;
    overflow: hidden;
  }

  .carousel-slide img {
    width: 100%;
    height: 100%;
    object-fit: contain;

    /* 🔑 CONTROLE DE ESTICADA */
    transform: scale(1.20, 2.80); /* X, Y */

    transform-origin: center center;
  }

  .arrow {
    width: 44px;
    height: 44px;
  }

  .arrow span {
    font-size: 22px;
  }
}

@media (max-width: 820px) {
  .carousel-slide img {
        transform: scale(1.20, 1.40); /* X, Y */
  }
}

@media (max-width: 768px) {
  .carousel-slide img {
        transform: scale(1.20, 1.50); /* X, Y */
  }
}

@media (max-width: 480px) {

  .carousel-slide img {
    aspect-ratio: 4 / 3; /* fica melhor em celular */
  }

  .arrow {
    width: 36px;
    height: 36px;
  }

  .arrow span {
    font-size: 18px;
  }

  .dots span {
    width: 10px;
    height: 10px;
  }
}

@media (max-width: 390px) {
  .carousel-slide img {
        transform: scale(1.20, 3.00); /* X, Y */
  }
}

@media (max-width: 375px) {
  .carousel-slide img {
        transform: scale(1.20, 3.10); /* X, Y */
  }
}

@media (orientation: landscape) and (max-height: 500px) {
  .carousel-slide img {
    transform: scale(1.20, 1.31); /* X, Y */    
  }
}
</style>
