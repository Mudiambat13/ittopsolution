<template>
    <div :class="['flex items-center', size === 'large' ? 'gap-4' : 'gap-2']">
      <!-- Icône -->
      <div :class="[
        'flex items-center justify-center rounded-lg bg-gradient-to-r from-[#646cff] to-[#42b883]',
        size === 'large' ? 'p-4' : 'p-2'
      ]">
        <svg 
          :class="[size === 'large' ? 'w-12 h-12' : 'w-6 h-6']"
          viewBox="0 0 24 24" 
          fill="none" 
          stroke="white" 
          stroke-width="2" 
          stroke-linecap="round" 
          stroke-linejoin="round"
        >
          <!-- Icône combinant outils et technologie -->
          <path d="M14.7 6.3a1 1 0 0 0 0 1.4l1.6 1.6a1 1 0 0 0 1.4 0l3.77-3.77a6 6 0 0 1-7.94 7.94l-6.91 6.91a2.12 2.12 0 0 1-3-3l6.91-6.91a6 6 0 0 1 7.94-7.94l-3.76 3.76z"/>
          <path d="M12 8l-5 5"/>
          <path d="M8 12l5-5"/>
          <!-- Cercle pour représenter la solution globale -->
          <circle cx="12" cy="12" r="9" stroke-dasharray="2 2"/>
        </svg>
      </div>
  
      <!-- Texte -->
      <div :class="['flex flex-col', size === 'large' ? 'gap-1' : 'gap-0']">
        <span :class="[
          'font-bold tracking-tight text-[#ffffffde]', 
          size === 'large' ? 'text-3xl' : 'text-xl'
        ]">
          IT TOP
        </span>
        <span :class="[
          'text-[#646cff] font-semibold', 
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