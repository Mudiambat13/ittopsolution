<script setup>
import { onMounted } from 'vue'

onMounted(() => {
  // Animation du titre avec un délai progressif
  const title = document.querySelector('.hero-title')
  const subtitle = document.querySelector('.hero-subtitle')
  const buttons = document.querySelectorAll('.hero-button')
  
  title.classList.add('animate-in')
  setTimeout(() => subtitle.classList.add('animate-in'), 500)
  buttons.forEach((button, index) => {
    setTimeout(() => button.classList.add('animate-in'), 1000 + (index * 200))
  })
})
</script>

<template>
  <div class="relative min-h-screen flex items-center overflow-hidden">
    <!-- Image de fond avec overlay renforcé -->
    <div class="absolute inset-0 z-0 hero-bg">
      <img 
        src="https://images.unsplash.com/photo-1558494949-ef010cbdcc31?q=80&w=1920" 
        alt="Background" 
        class="w-full h-full object-cover scale-110 animate-slow-zoom"
      />
      <div class="absolute inset-0 bg-gradient-to-r from-[#000000]/90 to-[#000000]/80"></div>
    </div>

    <!-- Contenu -->
    <div class="relative z-10 w-full max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-16 sm:py-24 md:py-32">
      <div class="max-w-3xl mx-auto text-center">
        <h1 class="hero-title opacity-0 text-4xl sm:text-5xl md:text-6xl lg:text-7xl font-bold text-white mb-4 sm:mb-6 drop-shadow-lg">
          Solutions IT <br class="hidden sm:block"/>
          <span class="bg-clip-text text-transparent bg-gradient-to-r from-[#646cff] to-[#42b883] animate-gradient drop-shadow-none">
            Professionnelles
          </span>
        </h1>
        
        <p class="hero-subtitle opacity-0 text-base sm:text-lg md:text-xl text-white mb-6 sm:mb-8 px-4 sm:px-0 drop-shadow-md font-medium">
          Expertise en vidéosurveillance, réseaux et maintenance informatique pour sécuriser et optimiser votre infrastructure
        </p>

        <!-- Boutons centrés avec animations améliorées -->
        <div class="flex flex-col sm:flex-row gap-3 sm:gap-4 justify-center px-4 sm:px-0">
          <a href="tel:+243991146003" 
             class="hero-button opacity-0 bg-[#646cff] hover:bg-[#747bff] px-6 py-3 rounded-full font-medium transition-all duration-300 text-white flex items-center justify-center gap-2 hover:scale-105 hover:shadow-lg hover:shadow-[#646cff]/25">
            <svg class="w-5 h-5 animate-pulse" fill="none" stroke="currentColor" viewBox="0 0 24 24">
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M3 5a2 2 0 012-2h3.28a1 1 0 01.948.684l1.498 4.493a1 1 0 01-.502 1.21l-2.257 1.13a11.042 11.042 0 005.516 5.516l1.13-2.257a1 1 0 011.21-.502l4.493 1.498a1 1 0 01.684.949V19a2 2 0 01-2 2h-1C9.716 21 3 14.284 3 6V5z" />
            </svg>
            <span>+243 991 146 003</span>
          </a>
          <a href="#services" 
             class="hero-button opacity-0 group border-2 border-white hover:border-[#646cff] hover:bg-[#646cff] px-6 py-3 rounded-full font-medium transition-all duration-300 text-white hover:scale-105 hover:shadow-lg hover:shadow-[#646cff]/25 flex items-center justify-center gap-2">
            <span>Nos Services</span>
            <svg class="w-5 h-5 transform group-hover:translate-y-0.5 transition-transform duration-300" fill="none" stroke="currentColor" viewBox="0 0 24 24">
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 14l-7 7m0 0l-7-7m7 7V3" />
            </svg>
          </a>
        </div>
      </div>
    </div>

    <!-- Effet de scroll amélioré -->
    <div class="absolute bottom-8 left-1/2 transform -translate-x-1/2 z-10 animate-fade-in-up">
      <div class="flex flex-col items-center space-y-4">
        <!-- Liens rapides -->
        <div class="flex gap-4 text-sm text-white/80">
          <a href="#services" class="hover:text-white transition-colors duration-300 flex items-center gap-1">
            <span>Services</span>
            <svg class="w-4 h-4" fill="none" stroke="currentColor" viewBox="0 0 24 24">
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 9l-7 7-7-7" />
            </svg>
          </a>
          <a href="#why-us" class="hover:text-white transition-colors duration-300 flex items-center gap-1">
            <span>Pourquoi nous</span>
            <svg class="w-4 h-4" fill="none" stroke="currentColor" viewBox="0 0 24 24">
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 9l-7 7-7-7" />
            </svg>
          </a>
        </div>
        
        <!-- Indicateur de scroll -->
        <div class="animate-bounce">
          <svg class="w-6 h-6 text-white/60" fill="none" stroke="currentColor" viewBox="0 0 24 24">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 14l-7 7m0 0l-7-7m7 7V3" />
          </svg>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
/* Animation du zoom lent sur l'image de fond */
@keyframes slow-zoom {
  from { transform: scale(1.1); }
  to { transform: scale(1); }
}

.animate-slow-zoom {
  animation: slow-zoom 20s ease-out forwards;
}

/* Animation du gradient */
@keyframes gradient {
  0% { background-position: 0% 50%; }
  50% { background-position: 100% 50%; }
  100% { background-position: 0% 50%; }
}

.animate-gradient {
  background-size: 200% 200%;
  animation: gradient 8s ease infinite;
}

/* Animations d'entrée */
@keyframes fade-in-up {
  from {
    opacity: 0;
    transform: translateY(20px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

.animate-in {
  animation: fade-in-up 0.8s ease-out forwards;
}

/* Animation de fade in pour le scroll indicator */
@keyframes fade-in {
  from { opacity: 0; }
  to { opacity: 1; }
}

.animate-fade-in-up {
  opacity: 0;
  animation: fade-in 1s ease-out 2s forwards;
}

/* Effet hover sur les boutons */
.hero-button {
  transition: all 0.3s ease;
}

.hero-button:hover {
  box-shadow: 0 0 20px rgba(100, 108, 255, 0.4);
}

/* Amélioration du contraste et de la lisibilité */
.text-white {
  text-shadow: 0 1px 2px rgba(0, 0, 0, 0.1);
}

/* Animation du survol des boutons */
.hero-button {
  transform: translateY(0);
  will-change: transform;
}

.hero-button:hover {
  transform: translateY(-2px);
}

/* Animation des liens rapides */
.animate-fade-in-up a {
  position: relative;
}

.animate-fade-in-up a::after {
  content: '';
  position: absolute;
  bottom: -2px;
  left: 0;
  width: 0;
  height: 1px;
  background-color: white;
  transition: width 0.3s ease;
}

.animate-fade-in-up a:hover::after {
  width: 100%;
}

/* Amélioration de l'accessibilité */
@media (prefers-reduced-motion: reduce) {
  .animate-slow-zoom,
  .animate-bounce,
  .animate-pulse {
    animation: none;
  }
  
  .hero-button:hover {
    transform: none;
  }
}

/* Amélioration du contraste sur mobile */
@media (max-width: 640px) {
  .hero-title,
  .hero-subtitle {
    text-shadow: 0 2px 4px rgba(0, 0, 0, 0.2);
  }
}
</style> 