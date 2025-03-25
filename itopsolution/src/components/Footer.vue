<template>
  <footer class="bg-[#1a1a1a] border-t border-[#ffffff1f]">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-12">
      <!-- Grille principale avec animation -->
      <div class="grid md:grid-cols-4 gap-8" v-motion-fade-visible>
        <!-- Logo et description -->
        <div class="col-span-2" v-motion-slide-visible-bottom>
          <div class="hover:scale-105 transition-transform duration-300 inline-block">
            <Logo />
          </div>
          <p class="mt-4 text-[#ffffffb3] hover:text-white transition-colors duration-300">
            Solutions technologiques professionnelles pour votre entreprise
          </p>
        </div>

        <!-- Services avec animations -->
        <div v-motion-slide-visible-bottom :delay="200">
          <h3 class="text-sm font-semibold text-[#646cff] uppercase tracking-wider mb-4">
            Services
          </h3>
          <ul class="space-y-2">
            <li v-for="(service, index) in ['Vidéosurveillance', 'Installation Serveur', 'Maintenance']" 
                :key="index"
                class="transform hover:translate-x-2 transition-all duration-300">
              <a href="#" 
                 class="text-[#ffffffb3] hover:text-[#646cff] transition-colors duration-300 flex items-center">
                <span class="mr-2">→</span>
                {{ service }}
              </a>
            </li>
          </ul>
        </div>

        <!-- Contact avec animations -->
        <div v-motion-slide-visible-bottom :delay="400">
          <h3 class="text-sm font-semibold text-[#646cff] uppercase tracking-wider mb-4">
            Contact
          </h3>
          <ul class="space-y-2">
            <li class="flex items-center text-[#ffffffb3] hover:text-[#646cff] transition-all duration-300 group">
              <svg class="w-4 h-4 mr-2 text-[#646cff] transform group-hover:rotate-12 transition-transform duration-300" 
                   fill="none" stroke="currentColor" viewBox="0 0 24 24">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M3 5a2 2 0 012-2h3.28a1 1 0 01.948.684l1.498 4.493a1 1 0 01-.502 1.21l-2.257 1.13a11.042 11.042 0 005.516 5.516l1.13-2.257a1 1 0 011.21-.502l4.493 1.498a1 1 0 01.684.949V19a2 2 0 01-2 2h-1C9.716 21 3 14.284 3 6V5z" />
              </svg>
              <span class="hover:translate-x-1 transition-transform duration-300 inline-block">
                +243 991 146 003
              </span>
            </li>
            <li class="flex items-center text-[#ffffffb3] hover:text-[#646cff] transition-all duration-300 group">
              <svg class="w-4 h-4 mr-2 text-[#646cff] transform group-hover:scale-110 transition-transform duration-300" 
                   fill="none" stroke="currentColor" viewBox="0 0 24 24">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M3 8l7.89 5.26a2 2 0 002.22 0L21 8M5 19h14a2 2 0 002-2V7a2 2 0 00-2-2H5a2 2 0 00-2 2v10a2 2 0 002 2z" />
              </svg>
              <span class="hover:translate-x-1 transition-transform duration-300 inline-block">
                ittopsolution04@gmail.com
              </span>
            </li>
          </ul>
        </div>
      </div>

      <!-- Copyright avec animation -->
      <div class="mt-8 pt-8 border-t border-[#ffffff1f]" v-motion-fade-visible :delay="600">
        <div class="flex flex-col md:flex-row justify-between items-center gap-4 text-[#ffffffb3] text-sm">
          <p>&copy; {{ new Date().getFullYear() }} IT Top Solution. Tous droits réservés.</p>
          <p class="flex items-center gap-2">
            Développé par 
            <a href="https://github.com/Mudiambat13" 
               target="_blank" 
               rel="noopener noreferrer" 
               class="text-[#646cff] hover:text-[#747bff] transition-all duration-300 hover:scale-105 transform inline-block">
              Jonathan Mudiambat
            </a>
          </p>
        </div>
      </div>
    </div>
  </footer>
</template>

<script setup>
import Logo from './Logo.vue'
</script>
