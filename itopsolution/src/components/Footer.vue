<template>
  <footer class="bg-[#1a1a1a] border-t border-[#ffffff1f]">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-8 sm:py-12">
      <!-- Grille principale -->
      <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-4 gap-8" v-motion-fade-visible>
        <!-- Logo et description -->
        <div class="col-span-1 sm:col-span-2 lg:col-span-2" v-motion-slide-visible-bottom>
          <div class="hover:scale-105 transition-transform duration-300 inline-block">
            <Logo />
          </div>
          <p class="mt-4 text-[#ffffffb3] hover:text-white transition-colors duration-300 flex items-start gap-2">
            <svg class="w-5 h-5 mt-1 text-[#646cff]" fill="none" stroke="currentColor" viewBox="0 0 24 24">
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M13 10V3L4 14h7v7l9-11h-7z" />
            </svg>
            <span>Solutions technologiques professionnelles pour votre entreprise</span>
          </p>
        </div>

        <!-- Services -->
        <div v-motion-slide-visible-bottom :delay="200">
          <h3 class="text-sm font-semibold text-[#646cff] uppercase tracking-wider mb-4 flex items-center gap-2">
            <svg class="w-5 h-5" fill="none" stroke="currentColor" viewBox="0 0 24 24">
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M21 13.255A23.931 23.931 0 0112 15c-3.183 0-6.22-.62-9-1.745M16 6V4a2 2 0 00-2-2h-4a2 2 0 00-2 2v2m4 6h.01M5 20h14a2 2 0 002-2V8a2 2 0 00-2-2H5a2 2 0 00-2 2v10a2 2 0 002 2z" />
            </svg>
            Services
          </h3>
          <ul class="space-y-3">
            <li class="transform hover:translate-x-2 transition-all duration-300">
              <a href="#services" class="text-[#ffffffb3] hover:text-[#646cff] transition-colors duration-300 flex items-center gap-2">
                <svg class="w-4 h-4 text-[#646cff]" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                  <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M15 10l4.553-2.276A1 1 0 0121 8.618v6.764a1 1 0 01-1.447.894L15 14M5 18h8a2 2 0 002-2V8a2 2 0 00-2-2H5a2 2 0 00-2 2v8a2 2 0 002 2z" />
                </svg>
                Vidéosurveillance
              </a>
            </li>
            <li class="transform hover:translate-x-2 transition-all duration-300">
              <a href="#services" class="text-[#ffffffb3] hover:text-[#646cff] transition-colors duration-300 flex items-center gap-2">
                <svg class="w-4 h-4 text-[#646cff]" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                  <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 12h14M5 12a2 2 0 01-2-2V6a2 2 0 012-2h14a2 2 0 012 2v4a2 2 0 01-2 2M5 12a2 2 0 00-2 2v4a2 2 0 002 2h14a2 2 0 002-2v-4a2 2 0 00-2-2m-2-4h.01M17 16h.01" />
                </svg>
                Installation Serveur
              </a>
            </li>
            <li class="transform hover:translate-x-2 transition-all duration-300">
              <a href="#services" class="text-[#ffffffb3] hover:text-[#646cff] transition-colors duration-300 flex items-center gap-2">
                <svg class="w-4 h-4 text-[#646cff]" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                  <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M10.325 4.317c.426-1.756 2.924-1.756 3.35 0a1.724 1.724 0 002.573 1.066c1.543-.94 3.31.826 2.37 2.37a1.724 1.724 0 001.065 2.572c1.756.426 1.756 2.924 0 3.35a1.724 1.724 0 00-1.066 2.573c.94 1.543-.826 3.31-2.37 2.37a1.724 1.724 0 00-2.572 1.065c-.426 1.756-2.924 1.756-3.35 0a1.724 1.724 0 00-2.573-1.066c-1.543.94-3.31-.826-2.37-2.37a1.724 1.724 0 00-1.065-2.572c-1.756-.426-1.756-2.924 0-3.35a1.724 1.724 0 001.066-2.573c-.94-1.543.826-3.31 2.37-2.37.996.608 2.296.07 2.572-1.065z" />
                  <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M15 12a3 3 0 11-6 0 3 3 0 016 0z" />
                </svg>
                Maintenance
              </a>
            </li>
          </ul>
        </div>

        <!-- Contact -->
        <div v-motion-slide-visible-bottom :delay="400">
          <h3 class="text-sm font-semibold text-[#646cff] uppercase tracking-wider mb-4 flex items-center gap-2">
            <svg class="w-5 h-5" fill="none" stroke="currentColor" viewBox="0 0 24 24">
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M3 8l7.89 5.26a2 2 0 002.22 0L21 8M5 19h14a2 2 0 002-2V7a2 2 0 00-2-2H5a2 2 0 00-2 2v10a2 2 0 002 2z" />
            </svg>
            Contact
          </h3>
          <ul class="space-y-3">
            <li>
              <a href="tel:+243991146003" class="group flex items-center text-[#ffffffb3] hover:text-[#646cff] transition-all duration-300">
                <div class="w-8 h-8 rounded-lg bg-[#646cff]/10 flex items-center justify-center mr-3 group-hover:bg-[#646cff]/20 transition-all duration-300">
                  <svg class="w-4 h-4 text-[#646cff] transform group-hover:rotate-12 transition-transform duration-300" 
                       fill="none" stroke="currentColor" viewBox="0 0 24 24">
                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M3 5a2 2 0 012-2h3.28a1 1 0 01.948.684l1.498 4.493a1 1 0 01-.502 1.21l-2.257 1.13a11.042 11.042 0 005.516 5.516l1.13-2.257a1 1 0 011.21-.502l4.493 1.498a1 1 0 01.684.949V19a2 2 0 01-2 2h-1C9.716 21 3 14.284 3 6V5z" />
                  </svg>
                </div>
                <span class="hover:translate-x-1 transition-transform duration-300">
                  +243 991 146 003
                </span>
              </a>
            </li>
            <li>
              <a href="mailto:ittopsolution04@gmail.com" class="group flex items-center text-[#ffffffb3] hover:text-[#646cff] transition-all duration-300">
                <div class="w-8 h-8 rounded-lg bg-[#646cff]/10 flex items-center justify-center mr-3 group-hover:bg-[#646cff]/20 transition-all duration-300">
                  <svg class="w-4 h-4 text-[#646cff] transform group-hover:scale-110 transition-transform duration-300" 
                       fill="none" stroke="currentColor" viewBox="0 0 24 24">
                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M3 8l7.89 5.26a2 2 0 002.22 0L21 8M5 19h14a2 2 0 002-2V7a2 2 0 00-2-2H5a2 2 0 00-2 2v10a2 2 0 002 2z" />
                  </svg>
                </div>
                <span class="hover:translate-x-1 transition-transform duration-300 break-all">
                  ittopsolution04@gmail.com
                </span>
              </a>
            </li>
            <li>
              <a href="#" class="group flex items-center text-[#ffffffb3] hover:text-[#646cff] transition-all duration-300">
                <div class="w-8 h-8 rounded-lg bg-[#646cff]/10 flex items-center justify-center mr-3 group-hover:bg-[#646cff]/20 transition-all duration-300">
                  <svg class="w-4 h-4 text-[#646cff] transform group-hover:scale-110 transition-transform duration-300" 
                       fill="none" stroke="currentColor" viewBox="0 0 24 24">
                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M17.657 16.657L13.414 20.9a1.998 1.998 0 01-2.827 0l-4.244-4.243a8 8 0 1111.314 0z" />
                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M15 11a3 3 0 11-6 0 3 3 0 016 0z" />
                  </svg>
                </div>
                <span class="hover:translate-x-1 transition-transform duration-300">
                  Kinshasa, RDC
                </span>
              </a>
            </li>
          </ul>
        </div>
      </div>

      <!-- Copyright -->
      <div class="mt-8 pt-8 border-t border-[#ffffff1f]" v-motion-fade-visible :delay="600">
        <div class="flex flex-col sm:flex-row justify-between items-center gap-4 text-[#ffffffb3] text-sm">
          <p class="text-center sm:text-left">&copy; {{ new Date().getFullYear() }} IT Top Solution. Tous droits réservés.</p>
          <p class="flex items-center gap-2">
            <span>Développé par</span>
            <a href="https://github.com/Mudiambat13" 
               target="_blank" 
               rel="noopener noreferrer" 
               class="text-[#646cff] hover:text-[#747bff] transition-all duration-300 hover:scale-105 transform inline-flex items-center gap-1">
              <svg class="w-4 h-4" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M10 20l4-16m4 4l4 4-4 4M6 16l-4-4 4-4" />
              </svg>
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
