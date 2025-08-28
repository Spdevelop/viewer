<template>
  <section class="relative min-h-screen flex items-center justify-center overflow-hidden py-20 p-10">
    <!-- Animated Background -->
    <div class="absolute inset-0 bg-gradient-to-br from-blue-50 via-indigo-50 to-purple-50 animate-gradient"></div>

    <!-- Floating Elements -->
    <div class="absolute inset-0 overflow-hidden">
      <div
        class="absolute top-20 left-20 w-72 h-72 bg-blue-200 rounded-full mix-blend-multiply filter blur-xl opacity-70 animate-float">
      </div>
      <div
        class="absolute top-40 right-20 w-72 h-72 bg-purple-200 rounded-full mix-blend-multiply filter blur-xl opacity-70 animate-float"
        style="animation-delay: -2s;"></div>
      <div
        class="absolute -bottom-8 left-40 w-72 h-72 bg-pink-200 rounded-full mix-blend-multiply filter blur-xl opacity-70 animate-float"
        style="animation-delay: -4s;"></div>
    </div>

    <!-- Content -->
    <div class="relative z-10 text-center px-4 sm:px-6 lg:px-8 w-full">
      <div class="container-custom">
        <!-- Main Headline -->
        <h1 class="text-5xl md:text-7xl font-bold mb-8 text-gradient animate-fade-in-up">
          Build Something
          <span class="block">Amazing</span>
        </h1>

        <!-- Subheadline -->
        <p class="text-xl md:text-2xl text-gray-600 mb-10 max-w-3xl mx-auto leading-relaxed animate-fade-in-up"
          style="animation-delay: 300ms;">
          Create stunning, animated experiences with modern web technologies.
          Transform your ideas into reality with our cutting-edge platform.
        </p>

        <!-- CTA Buttons -->
        <div class="flex flex-col sm:flex-row gap-6 justify-center items-center animate-fade-in-up"
          style="animation-delay: 600ms;">
          <button class="btn-primary">
            Get Started
          </button>
          <button class="btn-secondary">
            Learn More
          </button>
        </div>

      
      </div>
    </div>
  </section>
</template>

<script setup>
// Component logic here
</script>

<style scoped>
/* Component-specific styles */
</style>
