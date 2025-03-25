<template>
    <header class="fixed w-full top-0 z-50 border-b border-[#ffffff1f]" v-motion-fade-visible>
      <div class="bg-[#242424]/80 backdrop-blur supports-[backdrop-filter]:bg-[#242424]/60">
        <nav class="relative max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
          <div class="flex items-center h-16">
            <div class="flex-shrink-0 hover:scale-105 transition-transform duration-300">
              <Logo />
            </div>
            
            <div class="hidden md:flex flex-1 items-center justify-center">
              <div class="flex space-x-8">
                <a v-for="(link, index) in navLinks" :key="index" :href="link.href" 
                   class="nav-link text-sm text-[#ffffffde] hover:text-[#646cff] transition-all duration-300 relative"
                   v-motion-slide-visible-right
                   :delay="100 * index">
                  {{ link.name }}
                  <span class="absolute -bottom-1 left-0 w-0 h-0.5 bg-[#646cff] transition-all duration-300"></span>
                </a>
              </div>
            </div>
  
            <div class="flex-shrink-0 w-[76px] flex justify-end">
              <button @click="toggleMenu"
                class="md:hidden p-2 text-[#ffffffde] hover:text-[#646cff] rounded-lg focus:outline-none focus:ring-2 focus:ring-[#646cff] transition-all duration-300">
                <div class="relative w-6 h-5">
                  <span class="absolute w-6 h-0.5 bg-current transform transition-all duration-300"
                    :class="isMenuOpen ? 'rotate-45 top-2' : 'top-0'">
                  </span>
                  <span class="absolute w-6 h-0.5 bg-current top-2 transition-all duration-200"
                    :class="{ 'opacity-0': isMenuOpen }">
                  </span>
                  <span class="absolute w-6 h-0.5 bg-current transform transition-all duration-300"
                    :class="isMenuOpen ? '-rotate-45 top-2' : 'top-4'">
                  </span>
                </div>
              </button>
            </div>
          </div>
  
          <div class="fixed inset-0 bg-[#242424]/95 backdrop-blur-lg transition-all duration-500 ease-in-out md:hidden"
            :class="isMenuOpen ? 'opacity-100 translate-x-0' : 'opacity-0 translate-x-full'"
            style="top: 64px;">
            <div class="flex flex-col h-[calc(100vh-64px)] px-6 py-8 overflow-y-auto">
              <div class="flex flex-col space-y-6">
                <a v-for="(link, index) in navLinks" :key="index" :href="link.href" @click="closeMenu"
                   class="mobile-nav-link text-xl font-medium text-[#ffffffde] hover:text-[#646cff] transition-all duration-300 transform hover:translate-x-2"
                   :style="{ transitionDelay: `${index * 100}ms` }">
                  {{ link.name }}
                </a>
              </div>
              <div class="my-8 border-t border-[#ffffff1f]"></div>
              <div class="space-y-6">
                <h3 class="text-sm font-semibold text-[#646cff] uppercase tracking-wider">Contactez-nous</h3>
                <div class="space-y-4">
                  <a href="tel:+243991146003" class="block px-3 py-2 mt-4 text-center bg-[#646cff] hover:bg-[#747bff] rounded-full transition-all duration-300 text-white hover:scale-105 transform">
                    Appelez-nous
                  </a>
                  <a href="tel:+243979587427" class="flex items-center space-x-3 text-[#ffffffde] hover:text-[#646cff] transition-all duration-300 group">
                    <svg class="w-5 h-5 transform group-hover:rotate-12 transition-transform duration-300" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                      <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M3 5a2 2 0 012-2h3.28a1 1 0 01.948.684l1.498 4.493a1 1 0 01-.502 1.21l-2.257 1.13a11.042 11.042 0 005.516 5.516l1.13-2.257a1 1 0 011.21-.502l4.493 1.498a1 1 0 01.684.949V19a2 2 0 01-2 2h-1C9.716 21 3 14.284 3 6V5z" />
                    </svg>
                    <span>+243 979 587 427</span>
                  </a>
                </div>
                <a href="mailto:ittopsolution04@gmail.com" class="flex items-center space-x-3 text-[#ffffffde] hover:text-[#646cff] transition-colors duration-300">
                  <svg class="w-5 h-5" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M3 8l7.89 5.26a2 2 0 002.22 0L21 8M5 19h14a2 2 0 002-2V7a2 2 0 00-2-2H5a2 2 0 00-2 2v10a2 2 0 002 2z" />
                  </svg>
                  <span>ittopsolution04@gmail.com</span>
                </a>
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
  
  const closeMenu = () => {
    isMenuOpen.value = false
    document.body.style.overflow = ''
  }
  
  const handleKeydown = (event) => {
    if (event.key === 'Escape' && isMenuOpen.value) {
      closeMenu()
    }
  }
  
  onMounted(() => window.addEventListener('keydown', handleKeydown))
  onUnmounted(() => window.removeEventListener('keydown', handleKeydown))
  </script>
  
  <style scoped>
  .flex {
    justify-content: space-between;
  }
  
  .flex-shrink-0 {
    min-width: 76px;
  }
  
  .justify-center {
    justify-content: center;
  }
  
  @media (max-width: 768px) {
    .flex-shrink-0:last-child {
      justify-content: flex-end;
    }
    
    button {
      padding: 0.5rem;
    }
  }
  
  /* Animations pour les liens de navigation */
  .nav-link:hover span {
    width: 100%;
  }
  
  /* Animation pour le menu mobile */
  .mobile-nav-link {
    opacity: 0;
    transform: translateX(20px);
  }
  
  :deep(.menu-open) .mobile-nav-link {
    opacity: 1;
    transform: translateX(0);
  }
  
  /* Effet de glassmorphism amélioré */
  .backdrop-blur {
    backdrop-filter: blur(10px);
  }
  </style>