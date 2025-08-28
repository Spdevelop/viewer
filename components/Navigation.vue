<template>
  <nav class="fixed top-0 left-0 right-0 z-50 bg-white/80 backdrop-blur-md border-b border-gray-200">
    <div class="px-4 sm:px-6 lg:px-8">
      <div class="max-w-7xl mx-auto">
        <div class="flex items-center justify-between h-16">
          <!-- Logo -->
          <div class="flex items-center">
            <div class="text-2xl font-bold text-gradient">CompanyName</div>
          </div>

          <!-- Desktop Menu -->
          <div class="hidden md:flex items-center space-x-8">
            <a href="#features" class="text-gray-700 hover:text-blue-600 transition-colors duration-300">Features</a>
            <a href="#about" class="text-gray-700 hover:text-blue-600 transition-colors duration-300">About</a>
            <a href="#testimonials"
              class="text-gray-700 hover:text-blue-600 transition-colors duration-300">Testimonials</a>
            <a href="#pricing" class="text-gray-700 hover:text-blue-600 transition-colors duration-300">Pricing</a>
          </div>

          <!-- CTA Buttons -->
          <div class="hidden md:flex items-center space-x-4">
            <button class="text-gray-700 hover:text-blue-600 transition-colors duration-300">Sign In</button>
            <button class="btn-primary">Get Started</button>
          </div>

          <!-- Mobile Menu Button -->
          <button
            class="md:hidden p-2 rounded-md text-gray-700 hover:text-blue-600 hover:bg-gray-100 transition-colors duration-300">
            <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24">
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16M4 18h16"></path>
            </svg>
          </button>
        </div>
      </div>
    </div>
  </nav>
</template>

<script setup>
// Component logic here
</script>

<style scoped>
/* Additional component-specific styles if needed */
</style>
