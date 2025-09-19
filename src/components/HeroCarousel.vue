<template>
  <div class="back">
    <div id="inicio" class="carousel">
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
import img1 from '../assets/imagem1.jpg'
import img2 from '../assets/imagem2.jpg'
import img3 from '../assets/imagem3.jpg'

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

.carousel {
  width: 100%;
  margin: 0 auto;
  overflow: hidden;
  position: relative;
  box-shadow: 0 10px 30px rgba(0,0,0,0.2);
  margin-top: 30px;
  border-radius: 20px;
}

.back{
  padding: 20px;
  background-color: #fce2d6;
  box-shadow: 8px 0 20px rgba(0, 0, 0, 0.2), /* sombra direita */
              -8px 0 20px rgba(0, 0, 0, 0.2); /* sombra esquerda */
}

.carousel-track { display: flex; transition: transform 0.5s ease-in-out; }
.carousel-slide { 
  min-width: 100%;
  height: 600px;
  filter: brightness(95%);
}

.carousel-slide img {
  width: 100%;
  height: 100%; /* desktop */
  object-fit: cover;
  border-top-left-radius: 20px;
  border-top-right-radius: 20px;
  border-bottom-left-radius: 0;
  border-bottom-right-radius: 0;
  transition: transform 0.3s ease, filter 0.3s ease;
  filter: brightness(80%);
}

/* Setas */
.arrow {
  position: absolute;
  top: 50%;
  transform: translateY(-50%);
  background: rgba(255, 255, 255, 0.377);
  border: none;
  border-radius: 50%;
  width: 55px;
  height: 55px;
  display: flex;
  align-items: center;
  justify-content: center;
  cursor: pointer;
  transition: all 0.3s ease;
  z-index: 2;
  box-shadow: 0 4px 20px rgba(0,0,0,0.25);
}

.arrow span { font-size: 28px; color: #333; }
.arrow.left { left: 12px; }
.arrow.right { right: 12px; }

/* Dots */
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
  transition: all 0.3s ease;
}
.dots span.active {
  background: #ff7f32;
  transform: scale(1.4);
}

/* Mobile */
@media (max-width: 768px) {
  .carousel-slide img { height: 600px; }
  .arrow { width: 45px; height: 45px; }
  .arrow span { font-size: 22px; }
  .dots span { width: 12px; height: 12px; }
}

@media (max-width: 480px) {
  .carousel-slide img { height: 400px;}
  .arrow { width: 35px; height: 35px; }
  .arrow span { font-size: 18px; }
  .dots span { width: 10px; height: 10px; }
}
</style>
