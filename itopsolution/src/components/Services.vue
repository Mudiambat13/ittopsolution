<script setup>
import { ref, onMounted, reactive } from 'vue'
import { defineComponent } from 'vue'

// Importation des icônes
const CameraIcon = defineComponent({
  template: `
    <svg xmlns="http://www.w3.org/2000/svg" class="w-full h-full" fill="none" viewBox="0 0 24 24" stroke="currentColor">
      <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M15 10l4.553-2.276A1 1 0 0121 8.618v6.764a1 1 0 01-1.447.894L15 14M5 18h8a2 2 0 002-2V8a2 2 0 00-2-2H5a2 2 0 00-2 2v8a2 2 0 002 2z" />
    </svg>
  `
})

const ServerIcon = defineComponent({
  template: `
    <svg xmlns="http://www.w3.org/2000/svg" class="w-full h-full" fill="none" viewBox="0 0 24 24" stroke="currentColor">
      <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 12h14M5 12a2 2 0 01-2-2V6a2 2 0 012-2h14a2 2 0 012 2v4a2 2 0 01-2 2M5 12a2 2 0 00-2 2v4a2 2 0 002 2h14a2 2 0 002-2v-4a2 2 0 00-2-2m-2-4h.01M17 16h.01" />
    </svg>
  `
})

const ToolIcon = defineComponent({
  template: `
    <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24">
      <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M10.325 4.317c.426-1.756 2.924-1.756 3.35 0a1.724 1.724 0 002.573 1.066c1.543-.94 3.31.826 2.37 2.37a1.724 1.724 0 001.065 2.572c1.756.426 1.756 2.924 0 3.35a1.724 1.724 0 00-1.066 2.573c.94 1.543-.826 3.31-2.37 2.37a1.724 1.724 0 00-2.572 1.065c-.426 1.756-2.924 1.756-3.35 0a1.724 1.724 0 00-2.573-1.066c-1.543.94-3.31-.826-2.37-2.37a1.724 1.724 0 00-1.065-2.572c-1.756-.426-1.756-2.924 0-3.35a1.724 1.724 0 001.066-2.573c-.94-1.543.826-3.31 2.37-2.37.996.608 2.296.07 2.572-1.065z" />
      <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M15 12a3 3 0 11-6 0 3 3 0 016 0z" />
    </svg>
  `
})

const WifiIcon = defineComponent({
  template: `
    <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24">
      <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M8.111 16.404a5.5 5.5 0 017.778 0M12 20h.01m-7.08-7.071c3.904-3.905 10.236-3.905 14.141 0M1.394 9.393c5.857-5.857 15.355-5.857 21.213 0" />
    </svg>
  `
})

const ComputerIcon = defineComponent({
  template: `
    <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24">
      <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9.75 17L9 20l-1 1h8l-1-1-.75-3M3 13h18M5 17h14a2 2 0 002-2V5a2 2 0 00-2-2H5a2 2 0 00-2 2v10a2 2 0 002 2z" />
    </svg>
  `
})

const NetworkIcon = defineComponent({
  template: `
    <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24">
      <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6a2 2 0 012-2h2a2 2 0 012 2v2a2 2 0 01-2 2H6a2 2 0 01-2-2V6zM14 6a2 2 0 012-2h2a2 2 0 012 2v2a2 2 0 01-2 2h-2a2 2 0 01-2-2V6zM4 16a2 2 0 012-2h2a2 2 0 012 2v2a2 2 0 01-2 2H6a2 2 0 01-2-2v-2zM14 16a2 2 0 012-2h2a2 2 0 012 2v2a2 2 0 01-2 2h-2a2 2 0 01-2-2v-2z" />
    </svg>
  `
})

// Ajouter une nouvelle icône pour l'accompagnement
const ShoppingIcon = defineComponent({
  template: `
    <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24">
      <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M3 3h2l.4 2M7 13h10l4-8H5.4M7 13L5.4 5M7 13l-2.293 2.293c-.63.63-.184 1.707.707 1.707H17m0 0a2 2 0 100 4 2 2 0 000-4zm-8 2a2 2 0 11-4 0 2 2 0 014 0z" />
    </svg>
  `
})

const services = [
  {
    title: 'Caméras de Surveillance',
    description: 'Installation et configuration de systèmes de vidéosurveillance HD',
    image: 'https://images.unsplash.com/photo-1557862921-37829c790f19?q=80&w=500',
    icon: CameraIcon
  },
  {
    title: 'Installation Serveur',
    description: 'Mise en place et maintenance de serveurs professionnels',
    image: 'https://images.unsplash.com/photo-1558494949-ef010cbdcc31?q=80&w=500',
    icon: ServerIcon
  },
  {
    title: 'Réparations Avancées',
    description: 'Réparation d\'équipements informatiques modernes et industriels',
    image: 'https://images.unsplash.com/photo-1562408590-e32931084e23?q=80&w=500',
    icon: ToolIcon
  },
  {
    title: 'Points d\'accès Wi-Fi',
    description: 'Solutions Mikrotik avec gestion des accès et tickets personnalisés',
    image: 'https://images.unsplash.com/photo-1557862921-37829c790f19?q=80&w=500',
    icon: WifiIcon
  },
  {
    title: 'Maintenance Informatique',
    description: 'Service complet de maintenance et support technique',
    image: 'https://images.unsplash.com/photo-1539193143244-c83d9436d633?q=80&w=500',
    icon: ComputerIcon
  },
  {
    title: 'Configuration Réseau',
    description: 'Installation et optimisation de réseaux d\'entreprise',
    image: 'https://images.unsplash.com/photo-1544197150-b99a580bb7a8?q=80&w=500',
    icon: NetworkIcon
  },
  // Nouveau service ajouté
  {
    title: 'Accompagnement Matériel',
    description: 'Conseil et assistance dans le choix et l\'acquisition d\'équipements informatiques adaptés à vos besoins',
    image: 'https://images.unsplash.com/photo-1515378960530-7c0da6231fb1?q=80&w=500',
    icon: ShoppingIcon
  }
]

const selectedService = ref(null)
const isModalOpen = ref(false)

// Définition des features
const features = [
  {
    title: 'Expertise Technique',
    description: 'Plus de 10 ans d\'expérience dans le domaine des solutions IT professionnelles.',
    icon: 'M9 12l2 2 4-4m5.618-4.016A11.955 11.955 0 0112 2.944a11.955 11.955 0 01-8.618 3.04A12.02 12.02 0 003 9c0 5.591 3.824 10.29 9 11.622 5.176-1.332 9-6.03 9-11.622 0-1.042-.133-2.052-.382-3.016z'
  },
  {
    title: 'Support 24/7',
    description: 'Une équipe disponible en permanence pour répondre à vos besoins urgents.',
    icon: 'M12 8v4l3 3m6-3a9 9 0 11-18 0 9 9 0 0118 0z'
  },
  {
    title: 'Prix Compétitifs',
    description: 'Des solutions adaptées à votre budget avec un excellent rapport qualité-prix.',
    icon: 'M17 9V7a2 2 0 00-2-2H5a2 2 0 00-2 2v6a2 2 0 002 2h2m2 4h10a2 2 0 002-2v-6a2 2 0 00-2-2H9a2 2 0 00-2 2v6a2 2 0 002 2zm7-5a2 2 0 11-4 0 2 2 0 014 0z'
  },
  {
    title: 'Solutions Entreprise',
    description: 'Des solutions sur mesure pour les entreprises de toutes tailles.',
    icon: 'M19 21V5a2 2 0 00-2-2H7a2 2 0 00-2 2v16m14 0h2m-2 0h-5m-9 0H3m2 0h5M9 7h1m-1 4h1m4-4h1m-1 4h1m-5 10v-5a1 1 0 011-1h2a1 1 0 011 1v5m-4 0h4'
  }
]

// Simplification des stats
const stats = ref([
  { value: 0, target: 100, suffix: '+', label: 'Clients Satisfaits' },
  { value: 0, target: 500, suffix: '+', label: 'Projets Réalisés' },
  { value: 0, target: 24, suffix: '/7', label: 'Support Technique' },
  { value: 0, target: 10, suffix: '+', label: 'Années d\'Expérience' }
])

// Nouvelle fonction d'animation simplifiée
const animateStats = () => {
  stats.value.forEach(stat => {
    let current = 0
    const increment = stat.target / 50 // 50 étapes pour l'animation
    
    const interval = setInterval(() => {
      current += increment
      if (current >= stat.target) {
        stat.value = stat.target
        clearInterval(interval)
      } else {
        stat.value = Math.floor(current)
      }
    }, 40) // 40ms entre chaque étape = 2 secondes au total
  })
}

onMounted(() => {
  const observer = new IntersectionObserver((entries) => {
    entries.forEach(entry => {
      if (entry.isIntersecting) {
        animateStats()
        observer.disconnect()
      }
    })
  })

  const statsSection = document.querySelector('.stats-section')
  if (statsSection) {
    observer.observe(statsSection)
  }
})

const showServiceDetails = (service) => {
  selectedService.value = service
  isModalOpen.value = true
}

// Fonction pour obtenir les images contextuelles
const getServiceImage = (title) => {
  const images = {
    'Caméras de Surveillance': 'https://images.unsplash.com/photo-1555664424-778a1e5e1b48?q=80&w=1000', // Nouvelle image
    'Installation Serveur': 'https://images.unsplash.com/photo-1558494949-ef010cbdcc31?q=80&w=1000',
    'Réparations Avancées': 'https://images.unsplash.com/photo-1597872200969-2b65d56bd16b?q=80&w=1000',
    'Points d\'accès Wi-Fi': 'https://images.unsplash.com/photo-1606904825846-647eb07f5be2?q=80&w=1000',
    'Maintenance Informatique': 'https://images.unsplash.com/photo-1588508065123-287b28e013da?q=80&w=1000',
    'Configuration Réseau': 'https://images.unsplash.com/photo-1544197150-b99a580bb7a8?q=80&w=1000',
    'Accompagnement Matériel': 'https://images.unsplash.com/photo-1519389950473-47ba0277781c?q=80&w=1000'
  }
  return images[title]
}
</script>

<template>
  <section id="services" class="py-16 sm:py-24 relative overflow-hidden">
    <div class="absolute inset-0 -z-10">
      <div class="absolute inset-y-0 left-1/2 -translate-x-1/2 w-[200%] bg-[#646cff]/5"></div>
    </div>

    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      <h2 class="text-4xl font-bold text-center mb-16 bg-clip-text text-transparent bg-gradient-to-r from-[#646cff] to-[#42b883]">
        Nos Services
      </h2>
      
      <!-- Nouvelle disposition des services sans icônes -->
      <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
        <div v-for="(service, index) in services" 
             :key="service.title"
             class="group relative bg-[#1a1a1a] rounded-xl overflow-hidden hover:shadow-xl transition-all duration-300">
          <!-- Image de couverture -->
          <div class="relative h-48 overflow-hidden">
            <img :src="getServiceImage(service.title)" 
                 :alt="service.title"
                 loading="lazy"
                 class="w-full h-full object-cover transform group-hover:scale-105 transition-transform duration-500" />
            <div class="absolute inset-0 bg-gradient-to-t from-[#1a1a1a] to-transparent opacity-90"></div>
          </div>

          <!-- Contenu -->
          <div class="p-6">
            <h3 class="text-xl font-bold text-white mb-3 group-hover:text-[#646cff] transition-colors duration-300">
              {{ service.title }}
            </h3>
            <p class="text-[#ffffffcc] leading-relaxed group-hover:text-white transition-colors duration-300">
              {{ service.description }}
            </p>
          </div>

          <!-- Bordure animée -->
          <div class="absolute inset-0 border border-[#ffffff1f] rounded-xl group-hover:border-[#646cff]/50 transition-colors duration-300"></div>
        </div>
      </div>
    </div>

    <!-- Section Stats simplifiée -->
    <div class="stats-section mt-24 py-16 bg-[#646cff]/5">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <div class="grid grid-cols-2 md:grid-cols-4 gap-8">
          <div v-for="(stat, index) in stats" 
               :key="index"
               class="text-center">
            <div class="text-4xl font-bold text-[#646cff] mb-2">
              {{ stat.value }}{{ stat.suffix }}
            </div>
            <div class="text-[#ffffffb3]">{{ stat.label }}</div>
          </div>
        </div>
      </div>
    </div>

    <!-- Section Pourquoi nous choisir -->
    <div class="mt-24 max-w-4xl mx-auto px-4">
      <h3 class="text-3xl font-bold text-center mb-12 text-[#ffffffde]">
        Pourquoi Choisir IT Top Solution ?
      </h3>
      
      <div class="grid md:grid-cols-2 gap-8">
        <div v-for="(feature, index) in features" 
             :key="index"
             class="p-6 bg-[#1a1a1a] rounded-xl border border-[#ffffff1f] hover:border-[#646cff]/50 transition-colors">
          <div class="flex items-center gap-4 mb-4">
            <div class="h-10 w-10 rounded-lg bg-[#646cff]/10 flex items-center justify-center">
              <svg class="w-6 h-6 text-[#646cff]" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" :d="feature.icon" />
              </svg>
            </div>
            <h4 class="text-xl font-semibold text-[#ffffffde]">{{ feature.title }}</h4>
          </div>
          <p class="text-[#ffffffb3]">{{ feature.description }}</p>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.group {
  transform: translateZ(0);
}

.group:hover {
  transform: translateY(-2px);
  box-shadow: 0 10px 15px -3px rgba(100, 108, 255, 0.1), 0 4px 6px -2px rgba(100, 108, 255, 0.05);
}

/* Optimisation des images */
img {
  transform: translateZ(0);
  backface-visibility: hidden;
  -webkit-font-smoothing: antialiased;
}

@media (max-width: 768px) {
  .group {
    max-width: 400px;
    margin-left: auto;
    margin-right: auto;
  }
}

h3 {
  text-shadow: 0 1px 2px rgba(0,0,0,0.2);
}

.text-4xl {
  transition: none; /* Suppression de la transition pour éviter les conflits */
}

.stats-section {
  transform: translateZ(0);
}

.group svg {
  width: 2rem !important;
  height: 2rem !important;
  stroke-width: 2;
  stroke: #646cff !important;
}

/* Style pour le conteneur d'icône */
.h-16.w-16 {
  background-color: white;
  border: 2px solid #646cff;
  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
}

/* Effet au survol */
.group:hover .h-16.w-16 {
  background-color: #646cff;
}

.group:hover svg {
  stroke: white !important;
}
</style>