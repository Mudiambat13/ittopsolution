<template>
  <header class="fixed w-full top-0 z-50 border-b border-[#ffffff1f]" v-motion-fade-visible>
    <div class="bg-[#242424]/80 backdrop-blur supports-[backdrop-filter]:bg-[#242424]/60">
      <nav class="relative max-w-7xl mx-auto px-4">
        <div class="flex items-center h-16">
          <!-- Logo -->
          <div class="flex-shrink-0 hover:scale-105 transition-transform duration-300">
            <Logo />
          </div>
        </div>
      </nav>
    </div>
  </header>
</template>

<script setup>
import Logo from './Logo.vue'
</script>

<style scoped>
header {
  width: 100%;
}

.backdrop-blur {
  backdrop-filter: blur(10px);
}
</style>