<template>
  <section class="py-24 relative overflow-hidden">
    <!-- Effet de gradient d'arrière-plan -->
    <div class="absolute inset-0 -z-10">
      <div class="absolute inset-y-0 left-1/2 -translate-x-1/2 w-[200%] bg-[#646cff]/5"></div>
    </div>

    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      <h2 class="text-4xl font-bold text-center mb-16 bg-clip-text text-transparent bg-gradient-to-r from-[#646cff] to-[#42b883]">
        Ils nous font confiance
      </h2>

      <div class="grid md:grid-cols-2 gap-8">
        <!-- Kamoa Copper SA -->
        <div class="bg-[#1a1a1a] p-8 rounded-xl relative group hover:transform hover:scale-[1.02] transition-all duration-300">
          <div class="absolute top-0 right-0 transform translate-x-2 -translate-y-2">
            <svg class="w-12 h-12 text-[#646cff]/20" fill="currentColor" viewBox="0 0 32 32">
              <path d="M10 8v12h6v-4h-4v-8h-2zm12 0v12h6v-4h-4v-8h-2z"/>
            </svg>
          </div>
          
          <div class="relative">
            <p class="text-[#ffffffb3] mb-6 text-lg">
              "IT Top Solution a démontré une expertise exceptionnelle dans l'installation et la maintenance de nos systèmes de vidéosurveillance. Leur professionnalisme et leur réactivité ont été essentiels pour notre sécurité."
            </p>
            
            <div class="flex items-center">
              <div class="h-12 w-12 rounded-lg bg-[#646cff]/10 flex items-center justify-center">
                <svg class="w-6 h-6 text-[#646cff]" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                  <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 21V5a2 2 0 00-2-2H7a2 2 0 00-2 2v16m14 0h2m-2 0h-5m-9 0H3m2 0h5M9 7h1m-1 4h1m4-4h1m-1 4h1m-5 10v-5a1 1 0 011-1h2a1 1 0 011 1v5m-4 0h4"/>
                </svg>
              </div>
              <div class="ml-4">
                <p class="text-lg font-semibold text-[#ffffffde]">Kamoa Copper SA</p>
                <p class="text-sm text-[#646cff]">Entreprise minière</p>
              </div>
            </div>
          </div>
          
          <!-- Bordure gradient -->
          <div class="absolute inset-0 rounded-xl border border-[#ffffff1f] group-hover:border-[#646cff]/50 transition-colors duration-300"></div>
        </div>

        <!-- UAC SARL -->
        <div class="bg-[#1a1a1a] p-8 rounded-xl relative group hover:transform hover:scale-[1.02] transition-all duration-300">
          <div class="absolute top-0 right-0 transform translate-x-2 -translate-y-2">
            <svg class="w-12 h-12 text-[#646cff]/20" fill="currentColor" viewBox="0 0 32 32">
              <path d="M10 8v12h6v-4h-4v-8h-2zm12 0v12h6v-4h-4v-8h-2z"/>
            </svg>
          </div>
          
          <div class="relative">
            <p class="text-[#ffffffb3] mb-6 text-lg">
              "Une équipe technique hautement qualifiée qui a su mettre en place une infrastructure réseau performante et sécurisée. Leur service de maintenance est impeccable et leur support technique toujours disponible."
            </p>
            
            <div class="flex items-center">
              <div class="h-12 w-12 rounded-lg bg-[#646cff]/10 flex items-center justify-center">
                <svg class="w-6 h-6 text-[#646cff]" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                  <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M21 13.255A23.931 23.931 0 0112 15c-3.183 0-6.22-.62-9-1.745M16 6V4a2 2 0 00-2-2h-4a2 2 0 00-2 2v2m4 6h.01M5 20h14a2 2 0 002-2V8a2 2 0 00-2-2H5a2 2 0 00-2 2v10a2 2 0 002 2z"/>
                </svg>
              </div>
              <div class="ml-4">
                <p class="text-lg font-semibold text-[#ffffffde]">UAC SARL</p>
                <p class="text-sm text-[#646cff]">Solutions d'entreprise</p>
              </div>
            </div>
          </div>
          
          <!-- Bordure gradient -->
          <div class="absolute inset-0 rounded-xl border border-[#ffffff1f] group-hover:border-[#646cff]/50 transition-colors duration-300"></div>
        </div>
      </div>
    </div>
  </section>
</template>
