<script setup>
import { ref, onMounted } from 'vue'
import NavBar from './components/NavBar.vue'
import Hero from './components/Hero.vue'
import Services from './components/Services.vue'
import WhyUs from './components/WhyUs.vue'
import Testimonials from './components/Testimonials.vue'
import Contact from './components/Contact.vue'
import About from './components/About.vue'
import Footer from './components/Footer.vue'

const isLoading = ref(true)

onMounted(() => {
  // Attendre que toutes les images soient chargées
  window.addEventListener('load', () => {
    isLoading.value = false
  })
})
</script>

<template>
  <div class="min-h-screen bg-[#242424] text-[rgba(255,255,255,0.87)]">
    <NavBar />
    <main class="pt-16">
      <Hero />
      <Services />
      <About />
      <WhyUs />
      <Testimonials />
      <Contact />
    </main>
    <Footer />
  </div>
</template>

<style>
:root {
  --vt-c-white: #ffffff;
  --vt-c-white-soft: #f9f9f9;
  --vt-c-white-mute: #f1f1f1;

  --vt-c-black: #1a1a1a;
  --vt-c-black-soft: #242424;
  --vt-c-black-mute: #2f2f2f;

  --vt-c-indigo: #2c3e50;
  --vt-c-divider-light-1: rgba(60, 60, 60, 0.29);
  --vt-c-divider-light-2: rgba(60, 60, 60, 0.12);
  --vt-c-divider-dark-1: rgba(84, 84, 84, 0.65);
  --vt-c-divider-dark-2: rgba(84, 84, 84, 0.48);

  --vt-c-text-light-1: var(--vt-c-indigo);
  --vt-c-text-light-2: rgba(60, 60, 60, 0.66);
  --vt-c-text-dark-1: var(--vt-c-white);
  --vt-c-text-dark-2: rgba(235, 235, 235, 0.64);
}

:root {
  --color-background: var(--vt-c-black-soft);
  --color-background-soft: var(--vt-c-black-mute);
  --color-background-mute: var(--vt-c-gray-soft);

  --color-border: var(--vt-c-divider-dark-2);
  --color-border-hover: var(--vt-c-divider-dark-1);

  --color-heading: var(--vt-c-text-dark-1);
  --color-text: var(--vt-c-text-dark-2);
}

body {
  min-height: 100vh;
  color: var(--color-text);
  background: var(--color-background);
  line-height: 1.6;
  font-family: Inter, -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu,
    Cantarell, 'Fira Sans', 'Droid Sans', 'Helvetica Neue', sans-serif;
  font-size: 15px;
  text-rendering: optimizeLegibility;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}

html, body {
  overflow-x: hidden;
  width: 100%;
  margin: 0;
  padding: 0;
}

@media (max-width: 768px) {
  body {
    font-size: 14px;
  }
  
  .max-w-7xl {
    padding-left: 1rem;
    padding-right: 1rem;
  }
}

/* Styles globaux pour les images */
img {
  opacity: 1 !important;
  transition: opacity 0.3s ease-in-out;
}

/* Optionnel : Ajouter un placeholder pendant le chargement */
.image-placeholder {
  background: linear-gradient(110deg, #1a1a1a 8%, #2a2a2a 18%, #1a1a1a 33%);
  background-size: 200% 100%;
  animation: shimmer 1.5s linear infinite;
}

@keyframes shimmer {
  to {
    background-position: -200% 0;
  }
}
</style>
