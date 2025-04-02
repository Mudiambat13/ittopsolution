<template>
    <div :class="['flex items-center', size === 'large' ? 'gap-4' : 'gap-2']">
      <!-- Container du logo avec effets -->
      <div :class="[
        'logo-container relative overflow-hidden rounded-xl transition-all duration-300',
        size === 'large' ? 'p-4' : 'p-2',
        'hover:shadow-lg hover:shadow-[#646cff]/20 group'
      ]">
        <!-- Effets d'arrière-plan -->
        <div class="absolute inset-0">
          <!-- Gradient principal -->
          <div class="absolute inset-0 bg-gradient-to-br from-[#646cff] to-[#42b883] opacity-90"></div>
          <!-- Gradient animé -->
          <div class="absolute inset-0 bg-gradient-to-tr from-[#646cff]/50 to-transparent animate-gradient-slow"></div>
          <!-- Motif géométrique -->
          <div class="absolute inset-0 opacity-10">
            <div class="absolute inset-0 grid grid-cols-4 grid-rows-4">
              <div v-for="i in 16" :key="i" class="border border-white/20"></div>
            </div>
          </div>
        </div>

        <!-- Logo SVG principal -->
        <svg 
          :class="[
            'relative z-10 transition-transform duration-300 group-hover:scale-110',
            size === 'large' ? 'w-12 h-12' : 'w-6 h-6'
          ]"
          viewBox="0 0 24 24" 
          fill="none" 
          xmlns="http://www.w3.org/2000/svg"
        >
          <!-- Cercle externe -->
          <circle cx="12" cy="12" r="11" class="stroke-white" stroke-width="0.5" stroke-dasharray="2 2" />
          
          <!-- Hexagone -->
          <path 
            d="M12 4L18 8V16L12 20L6 16V8L12 4Z" 
            class="stroke-white fill-white/10" 
            stroke-width="0.5"
          />
          
          <!-- Lignes de circuit -->
          <path 
            class="animate-draw stroke-white" 
            d="M12 7v10M9 9l6 6M15 9l-6 6" 
            stroke-width="0.75"
          />
          
          <!-- Points de connexion -->
          <circle cx="12" cy="7" r="1" class="fill-white animate-pulse-subtle"/>
          <circle cx="12" cy="17" r="1" class="fill-white animate-pulse-subtle"/>
          <circle cx="9" cy="9" r="1" class="fill-white animate-pulse-subtle"/>
          <circle cx="15" cy="15" r="1" class="fill-white animate-pulse-subtle"/>
          <circle cx="15" cy="9" r="1" class="fill-white animate-pulse-subtle"/>
          <circle cx="9" cy="15" r="1" class="fill-white animate-pulse-subtle"/>
          
          <!-- Centre -->
          <circle cx="12" cy="12" r="2" class="fill-white/20 stroke-white" stroke-width="0.5"/>
          <circle cx="12" cy="12" r="1" class="fill-white animate-pulse"/>
        </svg>
      </div>
  
      <!-- Texte du logo -->
      <div :class="['flex flex-col', size === 'large' ? 'gap-1' : 'gap-0']">
        <span :class="[
          'font-bold tracking-tight bg-clip-text text-transparent bg-gradient-to-r from-white to-white/90', 
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
  background: radial-gradient(circle at center, rgba(255,255,255,0.1) 0%, transparent 70%);
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
  0% { opacity: 0.4; }
  50% { opacity: 1; }
  100% { opacity: 0.4; }
}

.animate-draw {
  animation: draw 3s ease-out forwards;
}

.animate-gradient-slow {
  animation: gradient-slow 8s ease-in-out infinite;
}

.animate-pulse-subtle {
  animation: pulse-subtle 2s ease-in-out infinite;
}

.animate-pulse {
  animation: pulse-subtle 1.5s ease-in-out infinite;
}
</style>