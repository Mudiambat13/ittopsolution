<template>
    <div :class="['flex items-center', size === 'large' ? 'gap-4' : 'gap-2']">
      <!-- Icône avec animation et effets -->
      <div :class="[
        'logo-container relative overflow-hidden rounded-xl transition-all duration-300',
        size === 'large' ? 'p-4' : 'p-2',
        'hover:shadow-lg hover:shadow-[#646cff]/20 group'
      ]">
        <!-- Fond animé -->
        <div class="absolute inset-0 bg-gradient-to-br from-[#646cff] to-[#42b883] opacity-90"></div>
        <div class="absolute inset-0 bg-gradient-to-tr from-[#646cff]/50 to-transparent animate-gradient-slow"></div>
        
        <!-- Motif géométrique en arrière-plan -->
        <div class="absolute inset-0 opacity-10">
          <div class="absolute inset-0 grid grid-cols-3 grid-rows-3">
            <div v-for="i in 9" :key="i" class="border border-white/20"></div>
          </div>
        </div>

        <!-- Logo principal -->
        <svg 
          :class="[
            'relative z-10 transition-transform duration-300 group-hover:scale-110',
            size === 'large' ? 'w-12 h-12' : 'w-6 h-6'
          ]"
          viewBox="0 0 24 24" 
          fill="none" 
          stroke="white" 
          stroke-width="1.5"
          stroke-linecap="round" 
          stroke-linejoin="round"
        >
          <!-- Circuit Board Pattern -->
          <path class="animate-draw" d="M12 2v4M12 18v4M4.93 4.93l2.83 2.83M16.24 16.24l2.83 2.83M2 12h4M18 12h4M4.93 19.07l2.83-2.83M16.24 7.76l2.83-2.83"/>
          
          <!-- Centre technologique -->
          <circle cx="12" cy="12" r="3" class="animate-pulse-subtle" fill="#ffffff33"/>
          <circle cx="12" cy="12" r="6" class="animate-spin-slow" stroke-dasharray="1 3"/>
          
          <!-- Éléments de connexion -->
          <path class="animate-draw-delayed" d="M12 9v6M9 12h6"/>
          <path class="animate-draw-delayed" d="M15 9l-6 6M9 9l6 6"/>
        </svg>
      </div>
  
      <!-- Texte avec effet de gradient -->
      <div :class="['flex flex-col', size === 'large' ? 'gap-1' : 'gap-0']">
        <span :class="[
          'font-bold tracking-tight bg-gradient-to-r from-white to-white/90 bg-clip-text text-transparent', 
          size === 'large' ? 'text-3xl' : 'text-xl'
        ]">
          IT TOP
        </span>
        <span :class="[
          'bg-gradient-to-r from-[#646cff] to-[#42b883] bg-clip-text text-transparent font-semibold', 
          size === 'large' ? 'text-xl' : 'text-sm'
        ]">
          SOLUTION
        </span>
      </div>
    </div>
  </template>
  
  <script setup>
  defineProps({
    size: {
      type: String,
      default: 'normal',
      validator: (value) => ['normal', 'large'].includes(value)
    }
  })
  </script>

<style scoped>
.logo-container {
  background: linear-gradient(135deg, #646cff 0%, #42b883 100%);
  transition: all 0.3s ease;
}

.logo-container::before {
  content: '';
  position: absolute;
  inset: 0;
  background: radial-gradient(circle at center, white/10%, transparent 70%);
  opacity: 0;
  transition: opacity 0.3s ease;
}

.logo-container:hover::before {
  opacity: 1;
}

@keyframes draw {
  from {
    stroke-dasharray: 20;
    stroke-dashoffset: 20;
  }
  to {
    stroke-dasharray: 20;
    stroke-dashoffset: 0;
  }
}

@keyframes gradient-slow {
  0% { transform: translate(0, 0); }
  50% { transform: translate(-10px, -10px); }
  100% { transform: translate(0, 0); }
}

@keyframes pulse-subtle {
  0% { opacity: 0.2; }
  50% { opacity: 0.4; }
  100% { opacity: 0.2; }
}

@keyframes spin-slow {
  from { transform: rotate(0deg); }
  to { transform: rotate(360deg); }
}

.animate-draw {
  animation: draw 3s ease-out forwards;
}

.animate-draw-delayed {
  animation: draw 2s ease-out 1s forwards;
}

.animate-gradient-slow {
  animation: gradient-slow 8s ease-in-out infinite;
}

.animate-pulse-subtle {
  animation: pulse-subtle 2s ease-in-out infinite;
}

.animate-spin-slow {
  transform-origin: center;
  animation: spin-slow 20s linear infinite;
}
</style>