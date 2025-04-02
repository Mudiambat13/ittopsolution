<script setup>
const contacts = {
  phones: ['+243 991 146 003', '+243 979 587 427'],
  email: 'ittopsolution04@gmail.com'
}
</script>

<template>
  <section id="contact" class="py-12 sm:py-24 relative overflow-hidden">
    <!-- Effet de gradient d'arrière-plan -->
    <div class="absolute inset-0 -z-10">
      <div class="absolute inset-y-0 left-1/2 -translate-x-1/2 w-[200%] bg-[#646cff]/5"></div>
    </div>

    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      <!-- Titre -->
      <h2 class="text-3xl sm:text-4xl font-bold text-center mb-8 sm:mb-16 bg-clip-text text-transparent bg-gradient-to-r from-[#646cff] to-[#42b883]">
        Contactez-nous
      </h2>

      <div class="grid gap-6 sm:gap-12">
        <!-- Informations de contact -->
        <div class="bg-[#1a1a1a] rounded-xl p-6 sm:p-8 border border-[#ffffff1f] relative group hover:border-[#646cff]/50 transition-colors duration-300">
          <h3 class="text-xl sm:text-2xl font-semibold mb-6 text-[#ffffffde] flex items-center gap-3">
            <span class="text-[#646cff]">
              <svg class="w-5 h-5 sm:w-6 sm:h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M17 8h2a2 2 0 012 2v6a2 2 0 01-2 2h-2v4l-4-4H9a1.994 1.994 0 01-1.414-.586m0 0L11 14h4a2 2 0 002-2V6a2 2 0 00-2-2H5a2 2 0 00-2 2v6a2 2 0 002 2h2v4l.586-.586z" />
              </svg>
            </span>
            Nos Coordonnées
          </h3>
          
          <!-- Téléphones -->
          <div class="mb-6 space-y-4">
            <h4 class="text-sm uppercase tracking-wider text-[#646cff] mb-3 flex items-center gap-2">
              <svg class="w-4 h-4" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M3 5a2 2 0 012-2h3.28a1 1 0 01.948.684l1.498 4.493a1 1 0 01-.502 1.21l-2.257 1.13a11.042 11.042 0 005.516 5.516l1.13-2.257a1 1 0 011.21-.502l4.493 1.498a1 1 0 01.684.949V19a2 2 0 01-2 2h-1C9.716 21 3 14.284 3 6V5z" />
              </svg>
              Téléphones
            </h4>
            <div class="space-y-3">
              <a v-for="phone in contacts.phones" 
                 :key="phone"
                 :href="`tel:${phone.replace(/\s/g, '')}`"
                 class="flex items-center group/item hover:bg-[#646cff]/5 p-3 rounded-lg transition-all duration-300">
                <div class="w-10 h-10 sm:w-12 sm:h-12 rounded-lg bg-[#646cff]/10 flex items-center justify-center mr-4 group-hover/item:bg-[#646cff]/20 transition-all duration-300 group-hover/item:scale-110">
                  <svg class="w-5 h-5 sm:w-6 sm:h-6 text-[#646cff]" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M3 5a2 2 0 012-2h3.28a1 1 0 01.948.684l1.498 4.493a1 1 0 01-.502 1.21l-2.257 1.13a11.042 11.042 0 005.516 5.516l1.13-2.257a1 1 0 011.21-.502l4.493 1.498a1 1 0 01.684.949V19a2 2 0 01-2 2h-1C9.716 21 3 14.284 3 6V5z" />
                  </svg>
                </div>
                <div class="flex flex-col">
                  <span class="text-sm sm:text-base text-[#ffffffde] group-hover/item:text-[#646cff] transition-colors duration-300 font-medium">
                    {{ phone }}
                  </span>
                  <span class="text-xs sm:text-sm text-[#ffffff80]">Disponible 24/7</span>
                </div>
              </a>
            </div>
          </div>

          <!-- Email -->
          <div>
            <h4 class="text-sm uppercase tracking-wider text-[#646cff] mb-3 flex items-center gap-2">
              <svg class="w-4 h-4" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M3 8l7.89 5.26a2 2 0 002.22 0L21 8M5 19h14a2 2 0 002-2V7a2 2 0 00-2-2H5a2 2 0 00-2 2v10a2 2 0 002 2z" />
              </svg>
              Email
            </h4>
            <a :href="`mailto:${contacts.email}`"
               class="flex items-center group/item hover:bg-[#646cff]/5 p-3 rounded-lg transition-all duration-300">
              <div class="w-10 h-10 sm:w-12 sm:h-12 rounded-lg bg-[#646cff]/10 flex items-center justify-center mr-4 group-hover/item:bg-[#646cff]/20 transition-all duration-300 group-hover/item:scale-110">
                <svg class="w-5 h-5 sm:w-6 sm:h-6 text-[#646cff]" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                  <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M3 8l7.89 5.26a2 2 0 002.22 0L21 8M5 19h14a2 2 0 002-2V7a2 2 0 00-2-2H5a2 2 0 00-2 2v10a2 2 0 002 2z" />
                </svg>
              </div>
              <div class="flex flex-col">
                <span class="text-sm sm:text-base text-[#ffffffde] group-hover/item:text-[#646cff] transition-colors duration-300 font-medium break-all">
                  {{ contacts.email }}
                </span>
                <span class="text-xs sm:text-sm text-[#ffffff80]">Réponse rapide garantie</span>
              </div>
            </a>
          </div>
        </div>

        <!-- Formulaire de contact -->
        <div class="bg-[#1a1a1a] rounded-xl p-6 sm:p-8 border border-[#ffffff1f] relative group hover:border-[#646cff]/50 transition-colors duration-300">
          <h3 class="text-xl sm:text-2xl font-semibold mb-6 text-[#ffffffde] flex items-center gap-3">
            <span class="text-[#646cff]">
              <svg class="w-5 h-5 sm:w-6 sm:h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M11 5H6a2 2 0 00-2 2v11a2 2 0 002 2h11a2 2 0 002-2v-5m-1.414-9.414a2 2 0 112.828 2.828L11.828 15H9v-2.828l8.586-8.586z" />
              </svg>
            </span>
            Envoyez-nous un message
          </h3>

          <form class="space-y-4 sm:space-y-6">
            <div class="relative group/input">
              <label for="name" class="block text-sm text-[#ffffffde] mb-2 flex items-center gap-2">
                <svg class="w-4 h-4 text-[#646cff]" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                  <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M16 7a4 4 0 11-8 0 4 4 0 018 0zM12 14a7 7 0 00-7 7h14a7 7 0 00-7-7z" />
                </svg>
                Nom complet
              </label>
              <input type="text" id="name" 
                     class="w-full px-4 py-3 bg-[#242424] border border-[#ffffff1f] rounded-lg focus:outline-none focus:border-[#646cff] text-[#ffffffde] transition-all duration-300">
            </div>

            <div class="relative group/input">
              <label for="email" class="block text-sm text-[#ffffffde] mb-2 flex items-center gap-2">
                <svg class="w-4 h-4 text-[#646cff]" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                  <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M3 8l7.89 5.26a2 2 0 002.22 0L21 8M5 19h14a2 2 0 002-2V7a2 2 0 00-2-2H5a2 2 0 00-2 2v10a2 2 0 002 2z" />
                </svg>
                Email
              </label>
              <input type="email" id="email" 
                     class="w-full px-4 py-3 bg-[#242424] border border-[#ffffff1f] rounded-lg focus:outline-none focus:border-[#646cff] text-[#ffffffde] transition-all duration-300">
            </div>

            <div class="relative group/input">
              <label for="message" class="block text-sm text-[#ffffffde] mb-2 flex items-center gap-2">
                <svg class="w-4 h-4 text-[#646cff]" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                  <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M8 10h.01M12 10h.01M16 10h.01M9 16H5a2 2 0 01-2-2V6a2 2 0 012-2h14a2 2 0 012 2v8a2 2 0 01-2 2h-5l-5 5v-5z" />
                </svg>
                Message
              </label>
              <textarea id="message" rows="4" 
                        class="w-full px-4 py-3 bg-[#242424] border border-[#ffffff1f] rounded-lg focus:outline-none focus:border-[#646cff] text-[#ffffffde] transition-all duration-300"></textarea>
            </div>

            <button type="submit"
                    class="w-full bg-[#646cff] hover:bg-[#747bff] text-white py-3 px-6 rounded-lg transition-all duration-300 font-medium flex items-center justify-center gap-2 group/button">
              <span>Envoyer</span>
              <svg class="w-5 h-5 transform group-hover/button:translate-x-1 transition-transform duration-300" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M14 5l7 7m0 0l-7 7m7-7H3" />
              </svg>
            </button>
          </form>
        </div>
      </div>
    </div>
  </section>
</template>