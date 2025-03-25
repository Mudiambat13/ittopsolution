<template>
    <header class="fixed w-full top-0 z-50 border-b border-[#ffffff1f]" v-motion-fade-visible>
      <div class="bg-[#242424]/80 backdrop-blur supports-[backdrop-filter]:bg-[#242424]/60">
        <nav class="relative max-w-7xl mx-auto px-4">
          <div class="flex items-center justify-between h-16">
            <div class="flex-shrink-0">
              <Logo />
            </div>
            
            <div class="hidden md:flex items-center justify-center flex-1">
              <div class="flex space-x-8">
                <a v-for="(link, index) in navLinks" :key="index" :href="link.href" 
                   class="text-sm text-[#ffffffde] hover:text-[#646cff] transition-all duration-300">
                  {{ link.name }}
                </a>
              </div>
            </div>
  
            <button @click="toggleMenu"
                    class="md:hidden inline-flex items-center justify-center p-2 text-[#ffffffde] hover:text-[#646cff] z-50">
              <div class="w-6 h-6 relative">
                <span class="absolute w-6 h-0.5 bg-current transform transition-all duration-300"
                      :class="isMenuOpen ? 'rotate-45 top-3' : 'top-1'"></span>
                <span class="absolute w-6 h-0.5 bg-current top-3 transition-all duration-200"
                      :class="{ 'opacity-0': isMenuOpen }"></span>
                <span class="absolute w-6 h-0.5 bg-current transform transition-all duration-300"
                      :class="isMenuOpen ? '-rotate-45 top-3' : 'top-5'"></span>
              </div>
            </button>
          </div>
  
          <div v-if="isMenuOpen"
               class="fixed inset-x-0 top-16 bottom-0 md:hidden bg-[#242424] transition-all duration-300">
            <div class="h-full overflow-y-auto px-4 py-6" @click.stop>
              <div class="flex flex-col space-y-4">
                <a v-for="(link, index) in navLinks" :key="index" :href="link.href"
                   class="text-lg text-[#ffffffde] hover:text-[#646cff] py-2 transition-all duration-300"
                   @click="handleLinkClick">
                  {{ link.name }}
                </a>
              </div>
              
              <div class="mt-8 pt-8 border-t border-[#ffffff1f]">
                <h3 class="text-sm font-semibold text-[#646cff] uppercase mb-4">
                  Contactez-nous
                </h3>
                <div class="space-y-4">
                  <a href="tel:+243991146003" 
                     @click="handleLinkClick"
                     class="block w-full text-center bg-[#646cff] hover:bg-[#747bff] px-6 py-3 rounded-full text-white transition-all duration-300">
                    Appelez-nous
                  </a>
                  <a href="tel:+243979587427" 
                     @click="handleLinkClick"
                     class="flex items-center space-x-3 text-[#ffffffde] hover:text-[#646cff] py-2 transition-all duration-300">
                    <svg class="w-5 h-5" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                      <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M3 5a2 2 0 012-2h3.28a1 1 0 01.948.684l1.498 4.493a1 1 0 01-.502 1.21l-2.257 1.13a11.042 11.042 0 005.516 5.516l1.13-2.257a1 1 0 011.21-.502l4.493 1.498a1 1 0 01.684.949V19a2 2 0 01-2 2h-1C9.716 21 3 14.284 3 6V5z" />
                    </svg>
                    <span>+243 979 587 427</span>
                  </a>
                </div>
              </div>
            </div>
          </div>
        </nav>
      </div>
    </header>
  </template>
  
  <script setup>
  import { ref, onMounted, onUnmounted } from 'vue'
  import Logo from './Logo.vue'
  
  const isMenuOpen = ref(false)
  const navLinks = [
    { name: 'Accueil', href: '#' },
    { name: 'Services', href: '#services' },
    { name: 'À propos', href: '#about' },
    { name: 'Contact', href: '#contact' }
  ]
  
  const toggleMenu = () => {
    isMenuOpen.value = !isMenuOpen.value
    document.body.style.overflow = isMenuOpen.value ? 'hidden' : ''
  }
  
  const handleLinkClick = () => {
    setTimeout(() => {
      isMenuOpen.value = false
      document.body.style.overflow = ''
    }, 150)
  }
  
  const handleClickOutside = (event) => {
    if (isMenuOpen.value && !event.target.closest('.md\\:hidden')) {
      isMenuOpen.value = false
      document.body.style.overflow = ''
    }
  }
  
  const handleScroll = () => {
    if (isMenuOpen.value) {
      isMenuOpen.value = false
      document.body.style.overflow = ''
    }
  }
  
  onMounted(() => {
    document.addEventListener('click', handleClickOutside)
    window.addEventListener('scroll', handleScroll)
  })
  
  onUnmounted(() => {
    document.removeEventListener('click', handleClickOutside)
    window.removeEventListener('scroll', handleScroll)
  })
  </script>
  
  <style scoped>
  /* Reset des styles par défaut */
  * {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
  }
  
  /* Styles de base */
  header {
    width: 100%;
    overflow-x: hidden;
  }
  
  /* Styles pour le menu mobile */
  @media (max-width: 768px) {
    .fixed {
      width: 100vw;
      left: 0;
      right: 0;
    }
    
    /* Empêcher le défilement horizontal */
    body {
      overflow-x: hidden;
      position: relative;
      width: 100%;
    }
    
    /* Ajuster la position du bouton menu */
    button {
      margin-right: 0;
      padding: 0.5rem;
    }
  }
  
  /* Animation du menu */
  .translate-x-full {
    transform: translateX(100%);
  }
  
  .translate-x-0 {
    transform: translateX(0);
  }
  
  /* Animation de transition */
  .transition-all {
    transition-property: all;
    transition-timing-function: cubic-bezier(0.4, 0, 0.2, 1);
    transition-duration: 300ms;
  }
  </style>