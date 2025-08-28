<template>
  <section class="section-padding bg-gray-50 py-24 p-10">
    <div class="container-custom">
      <div class="grid grid-cols-1 lg:grid-cols-2 gap-12 items-center">
        <!-- Image Column -->
        <div class="relative animate-slide-in-left">
          <div class="relative">
            <!-- Main Image -->
            <div
              class="w-full h-96 bg-gradient-to-br from-blue-400 to-purple-600 rounded-2xl shadow-2xl transform rotate-3 hover:rotate-0 transition-transform duration-500">
              <div
                class="absolute inset-0 bg-gradient-to-br from-blue-500/20 to-purple-600/20 rounded-2xl flex items-center justify-center">
                <div class="text-white text-6xl font-bold opacity-20">🚀</div>
              </div>
            </div>
            <!-- Floating Elements -->
            <div class="absolute -top-4 -right-4 w-24 h-24 bg-yellow-400 rounded-full shadow-lg animate-float"></div>
            <div class="absolute -bottom-4 -left-4 w-16 h-16 bg-pink-400 rounded-full shadow-lg animate-float"
              style="animation-delay: -2s;"></div>
          </div>
        </div>

        <!-- Text Column -->
        <div class="space-y-8 animate-slide-in-right" style="animation-delay: 300ms;">
          <h2 class="text-4xl md:text-5xl font-bold text-gradient">
            About Our Mission
          </h2>
          <p class="text-lg text-gray-600 leading-relaxed">
            Lorem ipsum dolor sit amet, consectetur adipiscing elit. Sed do eiusmod tempor incididunt ut labore et
            dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip
            ex ea commodo consequat.
          </p>
          <p class="text-lg text-gray-600 leading-relaxed">
            Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
            Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est
            laborum.
          </p>

          <!-- Stats -->
          <div class="grid grid-cols-3 gap-6 pt-8">
            <div v-for="(stat, index) in stats" :key="index" class="text-center animate-fade-in-up"
              :style="{ animationDelay: `${600 + index * 100}ms` }">
              <div class="text-3xl font-bold text-blue-600 mb-2">{{ stat.value }}</div>
              <div class="text-sm text-gray-600">{{ stat.label }}</div>
            </div>
          </div>

          <!-- CTA Button -->
          <div class="pt-8 animate-fade-in-up" style="animation-delay: 900ms;">
            <button class="btn-primary">
              Learn More About Us
            </button>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
// Stats data
const stats = [
  { value: '10K+', label: 'Happy Users' },
  { value: '99.9%', label: 'Uptime' },
  { value: '24/7', label: 'Support' }
]
</script>

<style scoped>
/* Component-specific styles */
</style>
