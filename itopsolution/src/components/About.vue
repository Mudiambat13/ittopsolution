<template>
  <section id="about" class="py-16 sm:py-24 relative overflow-hidden">
    <!-- Effet de gradient d'arrière-plan -->
    <div class="absolute inset-0 -z-10">
      <div class="absolute inset-y-0 left-1/2 -translate-x-1/2 w-[200%] bg-[#646cff]/5"></div>
    </div>

    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      <!-- En-tête de la section -->
      <h2 class="text-4xl font-bold text-center mb-16 bg-clip-text text-transparent bg-gradient-to-r from-[#646cff] to-[#42b883]">
        À Propos de Nous
      </h2>

      <!-- Contenu principal -->
      <div class="grid md:grid-cols-2 gap-12 items-center">
        <!-- Image de l'entreprise -->
        <div class="relative group">
          <div class="overflow-hidden rounded-xl">
            <img 
              src="https://images.unsplash.com/photo-1504384764586-bb4cdc1707b0?q=80&w=1000" 
              alt="IT Top Solution Team" 
              class="w-full rounded-xl transform group-hover:scale-105 transition-transform duration-500"
            />
          </div>
        </div>

        <!-- Texte de présentation -->
        <div class="space-y-6">
          <h3 class="text-2xl font-semibold text-[#ffffffde]">
            Votre Partenaire Technologique de Confiance
          </h3>
          
          <p class="text-[#ffffffb3] leading-relaxed">
            IT Top Solution est une entreprise leader dans le domaine des solutions informatiques, 
            spécialisée dans l'installation de systèmes de vidéosurveillance, la configuration de 
            serveurs et la maintenance informatique.
          </p>

          <p class="text-[#ffffffb3] leading-relaxed">
            Depuis notre création, nous nous engageons à fournir des services de haute qualité et 
            des solutions personnalisées pour répondre aux besoins spécifiques de chaque client.
          </p>

          <!-- Points forts -->
          <div class="space-y-4 pt-4">
            <div class="flex items-center gap-3">
              <div class="h-8 w-8 rounded-lg bg-[#646cff]/10 flex items-center justify-center">
                <svg class="w-5 h-5 text-[#646cff]" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                  <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 13l4 4L19 7" />
                </svg>
              </div>
              <span class="text-[#ffffffde]">Service client exceptionnel</span>
            </div>

            <div class="flex items-center gap-3">
              <div class="h-8 w-8 rounded-lg bg-[#646cff]/10 flex items-center justify-center">
                <svg class="w-5 h-5 text-[#646cff]" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                  <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 13l4 4L19 7" />
                </svg>
              </div>
              <span class="text-[#ffffffde]">Expertise technique approfondie</span>
            </div>

            <div class="flex items-center gap-3">
              <div class="h-8 w-8 rounded-lg bg-[#646cff]/10 flex items-center justify-center">
                <svg class="w-5 h-5 text-[#646cff]" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                  <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 13l4 4L19 7" />
                </svg>
              </div>
              <span class="text-[#ffffffde]">Solutions personnalisées</span>
            </div>
          </div>

          <!-- Bouton d'action -->
          <div class="pt-6">
            <a href="#contact" 
               class="inline-flex items-center px-6 py-3 bg-[#646cff] hover:bg-[#747bff] rounded-full text-white transition-colors duration-300">
              Contactez-nous
              <svg class="w-5 h-5 ml-2" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M14 5l7 7m0 0l-7 7m7-7H3" />
              </svg>
            </a>
          </div>
        </div>
      </div>

      <!-- Section Mission et Vision -->
      <div class="grid md:grid-cols-2 gap-8 mt-24">
        <div class="p-8 bg-[#1a1a1a] rounded-xl border border-[#ffffff1f] hover:border-[#646cff]/50 transition-colors">
          <h3 class="text-xl font-semibold text-[#ffffffde] mb-4">Notre Mission</h3>
          <p class="text-[#ffffffb3]">
            Fournir des solutions technologiques innovantes et fiables qui permettent à nos clients 
            d'optimiser leurs opérations et de sécuriser leurs infrastructures informatiques.
          </p>
        </div>

        <div class="p-8 bg-[#1a1a1a] rounded-xl border border-[#ffffff1f] hover:border-[#646cff]/50 transition-colors">
          <h3 class="text-xl font-semibold text-[#ffffffde] mb-4">Notre Vision</h3>
          <p class="text-[#ffffffb3]">
            Devenir le partenaire technologique de référence en RDC, reconnu pour notre excellence, 
            notre innovation et notre engagement envers la satisfaction client.
          </p>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
// Suppression des imports GSAP
</script>

<style scoped>
/* Garder uniquement les transitions CSS simples */
.group img {
  transition: transform 0.5s ease;
}

.group:hover img {
  transform: scale(1.05);
}
</style>
