<script setup>
const contacts = {
  phones: ['+243 991 146 003', '+243 979 587 427'],
  email: 'ittopsolution04@gmail.com'
}
</script>

<template>
  <section id="contact" class="py-24 relative">
    <!-- Effet de gradient d'arrière-plan -->
    <div class="absolute inset-0 -z-10">
      <div class="absolute inset-y-0 left-1/2 -translate-x-1/2 w-[200%] bg-[#646cff]/5"></div>
    </div>

    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      <h2 class="text-4xl font-bold text-center mb-16 bg-clip-text text-transparent bg-gradient-to-r from-[#646cff] to-[#42b883]">
        Contactez-nous
      </h2>

      <div class="grid md:grid-cols-2 gap-12">
        <!-- Informations de contact -->
        <div class="bg-[#1a1a1a] rounded-xl p-8 border border-[#ffffff1f]">
          <h3 class="text-2xl font-semibold mb-6 text-[#ffffffde]">Nos Coordonnées</h3>
          
          <!-- Téléphones -->
          <div class="mb-8">
            <h4 class="text-sm uppercase tracking-wider text-[#646cff] mb-3">Téléphones</h4>
            <div class="space-y-2">
              <a 
                v-for="phone in contacts.phones" 
                :key="phone"
                :href="`tel:${phone.replace(/\s/g, '')}`"
                class="flex items-center group"
              >
                <div class="w-10 h-10 rounded-lg bg-[#646cff]/10 flex items-center justify-center mr-4 group-hover:bg-[#646cff]/20 transition-colors duration-300">
                  <svg class="w-5 h-5 text-[#646cff]" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M3 5a2 2 0 012-2h3.28a1 1 0 01.948.684l1.498 4.493a1 1 0 01-.502 1.21l-2.257 1.13a11.042 11.042 0 005.516 5.516l1.13-2.257a1 1 0 011.21-.502l4.493 1.498a1 1 0 01.684.949V19a2 2 0 01-2 2h-1C9.716 21 3 14.284 3 6V5z" />
                  </svg>
                </div>
                <span class="text-[#ffffffde] group-hover:text-[#646cff] transition-colors duration-300">
                  {{ phone }}
                </span>
              </a>
            </div>
          </div>

          <!-- Email -->
          <div>
            <h4 class="text-sm uppercase tracking-wider text-[#646cff] mb-3">Email</h4>
            <a 
              :href="`mailto:${contacts.email}`"
              class="flex items-center group"
            >
              <div class="w-10 h-10 rounded-lg bg-[#646cff]/10 flex items-center justify-center mr-4 group-hover:bg-[#646cff]/20 transition-colors duration-300">
                <svg class="w-5 h-5 text-[#646cff]" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                  <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M3 8l7.89 5.26a2 2 0 002.22 0L21 8M5 19h14a2 2 0 002-2V7a2 2 0 00-2-2H5a2 2 0 00-2 2v10a2 2 0 002 2z" />
                </svg>
              </div>
              <span class="text-[#ffffffde] group-hover:text-[#646cff] transition-colors duration-300">
                {{ contacts.email }}
              </span>
            </a>
          </div>
        </div>

        <!-- Formulaire de contact -->
        <div class="bg-[#1a1a1a] rounded-xl p-8 border border-[#ffffff1f]">
          <h3 class="text-2xl font-semibold mb-6 text-[#ffffffde]">Envoyez-nous un message</h3>
          <form class="space-y-6">
            <div>
              <label for="name" class="block text-sm text-[#ffffffde] mb-2">Nom complet</label>
              <input 
                type="text" 
                id="name" 
                class="w-full px-4 py-2 bg-[#242424] border border-[#ffffff1f] rounded-lg focus:outline-none focus:border-[#646cff] text-[#ffffffde]"
              >
            </div>
            <div>
              <label for="email" class="block text-sm text-[#ffffffde] mb-2">Email</label>
              <input 
                type="email" 
                id="email" 
                class="w-full px-4 py-2 bg-[#242424] border border-[#ffffff1f] rounded-lg focus:outline-none focus:border-[#646cff] text-[#ffffffde]"
              >
            </div>
            <div>
              <label for="message" class="block text-sm text-[#ffffffde] mb-2">Message</label>
              <textarea 
                id="message" 
                rows="4" 
                class="w-full px-4 py-2 bg-[#242424] border border-[#ffffff1f] rounded-lg focus:outline-none focus:border-[#646cff] text-[#ffffffde]"
              ></textarea>
            </div>
            <button 
              type="submit"
              class="w-full bg-[#646cff] hover:bg-[#747bff] text-white py-2 px-4 rounded-lg transition-colors duration-300 font-medium">
              Envoyer le message
            </button>
          </form>
        </div>
      </div>
    </div>
  </section>
</template>