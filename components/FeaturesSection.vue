<template>
  <section class="section-padding bg-white py-24 p-10">
    <div class="container-custom">
      <!-- Section Header -->
      <div class="text-center mb-20 animate-fade-in-up">
        <h2 class="text-4xl md:text-5xl font-bold mb-6 text-gradient">
          Powerful Features
        </h2>
        <p class="text-xl text-gray-600 max-w-2xl mx-auto">
          Everything you need to create exceptional digital experiences
        </p>
      </div>

      <!-- Features Grid -->
      <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
        <div v-for="(feature, index) in features" :key="index"
          class="group bg-white rounded-2xl p-8 shadow-lg hover:shadow-2xl transition-all duration-500 transform hover:-translate-y-2 border border-gray-100 animate-fade-in-up"
          :style="{ animationDelay: `${index * 100}ms` }">
          <!-- Icon -->
          <div
            class="w-16 h-16 bg-gradient-to-br from-blue-500 to-purple-600 rounded-2xl flex items-center justify-center mb-6 group-hover:scale-110 transition-transform duration-300">
            <component :is="feature.icon" class="w-8 h-8 text-white" />
          </div>
          <!-- Title -->
          <h3 class="text-xl font-semibold mb-4 text-gray-900 group-hover:text-blue-600 transition-colors duration-300">
            {{ feature.title }}</h3>
          <!-- Description -->
          <p class="text-gray-600 leading-relaxed">{{ feature.description }}</p>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import { h } from 'vue'

// Feature data
const features = [
  {
    icon: 'IconRocket',
    title: 'Lightning Fast',
    description: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.'
  },
  {
    icon: 'IconShield',
    title: 'Secure & Reliable',
    description: 'Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.'
  },
  {
    icon: 'IconZap',
    title: 'High Performance',
    description: 'Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.'
  },
  {
    icon: 'IconGlobe',
    title: 'Global Reach',
    description: 'Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.'
  },
  {
    icon: 'IconHeart',
    title: 'User Centric',
    description: 'Sed ut perspiciatis unde omnis iste natus error sit voluptatem accusantium doloremque laudantium.'
  },
  {
    icon: 'IconStar',
    title: 'Premium Quality',
    description: 'Nemo enim ipsam voluptatem quia voluptas sit aspernatur aut odit aut fugit, sed quia consequuntur.'
  }
]

// Simple icon components
const IconRocket = () => h('svg', { fill: 'currentColor', viewBox: '0 0 24 24' }, [
  h('path', { d: 'M12 2L2 7l10 5 10-5-10-5zM2 17l10 5 10-5M2 12l10 5 10-5' })
])

const IconShield = () => h('svg', { fill: 'currentColor', viewBox: '0 0 24 24' }, [
  h('path', { d: 'M12 1l3.09 6.26L22 9.27l-5 4.87 1.18 6.88L12 17.77l-6.18 3.25L7 14.14 2 9.27l6.91-2.01L12 1z' })
])

const IconZap = () => h('svg', { fill: 'currentColor', viewBox: '0 0 24 24' }, [
  h('path', { d: 'M13 2L3 14h9l-1 8 10-12h-9l1-8z' })
])

const IconGlobe = () => h('svg', { fill: 'currentColor', viewBox: '0 0 24 24' }, [
  h('path', { d: 'M12 2C6.48 2 2 6.48 2 12s4.48 10 10 10 10-4.48 10-10S17.52 2 12 2zm-1 17.93c-3.94-.49-7-3.85-7-7.93 0-.62.08-1.21.21-1.79L9 15v1c0 1.1.9 2 2 2v1.93zm6.9-2.54c-.26-.81-1.08-1.39-1.9-1.39h-1v-3c0-.55-.45-1-1-1H8v-2h2c.55 0 1-.45 1-1V7h2c1.1 0 2-.9 2-2v-.41c2.93 1.19 5 4.06 5 7.41 0 2.08-.8 3.97-2.1 5.39z' })
])

const IconHeart = () => h('svg', { fill: 'currentColor', viewBox: '0 0 24 24' }, [
  h('path', { d: 'M12 21.35l-1.45-1.32C5.4 15.36 2 12.28 2 8.5 2 5.42 4.42 3 7.5 3c1.74 0 3.41.81 4.5 2.09C13.09 3.81 14.76 3 16.5 3 19.58 3 22 5.42 22 8.5c0 3.78-3.4 6.86-8.55 11.54L12 21.35z' })
])

const IconStar = () => h('svg', { fill: 'currentColor', viewBox: '0 0 24 24' }, [
  h('path', { d: 'M12 17.27L18.18 21l-1.64-7.03L22 9.24l-7.19-.61L12 2 9.19 8.63 2 9.24l5.46 4.73L5.82 21z' })
])
</script>

<style scoped>
/* Component-specific styles */
</style>
