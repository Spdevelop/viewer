<template>
  <section class="section-padding bg-white py-24 p-10">
    <div class="container-custom">
      <!-- Section Header -->
      <div class="text-center mb-20 animate-fade-in-up">
        <h2 class="text-4xl md:text-5xl font-bold mb-6 text-gradient">
          What Our Users Say
        </h2>
        <p class="text-xl text-gray-600 max-w-2xl mx-auto">
          Don't just take our word for it - hear from our satisfied customers
        </p>
      </div>

      <!-- Testimonials Grid -->
      <div class="grid grid-cols-1 md:grid-cols-3 gap-8 mb-16">
        <div v-for="(testimonial, index) in testimonials" :key="index"
          class="group bg-gray-50 rounded-2xl p-8 shadow-lg hover:shadow-xl transition-all duration-500 transform hover:-translate-y-2 border border-gray-100 animate-fade-in-up"
          :style="{ animationDelay: `${index * 200}ms` }">
          <!-- Quote Icon -->
          <div class="text-4xl text-blue-500 mb-4">"</div>
          
          <!-- Testimonial Text -->
          <p class="text-gray-700 leading-relaxed mb-6 italic">
            {{ testimonial.quote }}
          </p>
          
          <!-- Author Info -->
          <div class="flex items-center">
            <!-- Avatar -->
            <div
              class="w-12 h-12 bg-gradient-to-br from-blue-500 to-purple-600 rounded-full flex items-center justify-center text-white font-bold text-lg mr-4">
              {{ testimonial.avatar }}
            </div>
            
            <!-- Name and Role -->
            <div>
              <div class="font-semibold text-gray-900">{{ testimonial.name }}</div>
              <div class="text-sm text-gray-600">{{ testimonial.role }}</div>
            </div>
          </div>
          
          <!-- Rating Stars -->
          <div class="flex items-center mt-4">
            <div v-for="star in 5" :key="star" class="text-yellow-400 text-lg">
              ★
            </div>
          </div>
        </div>
      </div>

      <!-- View All Button -->
      <div class="text-center mt-16 animate-fade-in-up" style="animation-delay: 800ms;">
        <button 
          @click="viewAllTestimonials"
          class="group relative inline-flex items-center justify-center px-8 py-4 text-lg font-semibold text-white bg-gradient-to-r from-blue-600 via-purple-600 to-indigo-600 rounded-full shadow-lg hover:shadow-xl transform hover:-translate-y-1 hover:scale-105 transition-all duration-300 ease-out overflow-hidden before:absolute before:inset-0 before:bg-gradient-to-r before:from-blue-700 before:via-purple-700 before:to-indigo-700 before:opacity-0 before:transition-opacity before:duration-300 hover:before:opacity-100"
        >
          <!-- Button Background Shine Effect -->
          <div class="absolute inset-0 bg-gradient-to-r from-transparent via-white/20 to-transparent -skew-x-12 -translate-x-full group-hover:translate-x-full transition-transform duration-1000 ease-out"></div>
          
          <!-- Button Content -->
          <span class="relative z-10 flex items-center space-x-2">
            <span v-if="!isLoading">View All Testimonials</span>
            <span v-else class="flex items-center space-x-2">
              <svg class="animate-spin h-5 w-5 text-white" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24">
                <circle class="opacity-25" cx="12" cy="12" r="10" stroke="currentColor" stroke-width="4"></circle>
                <path class="opacity-75" fill="currentColor" d="M4 12a8 8 0 018-8V0C5.373 0 0 5.373 0 12h4zm2 5.291A7.962 7.962 0 014 12H0c0 3.042 1.135 5.824 3 7.938l3-2.647z"></path>
              </svg>
              <span>Loading...</span>
            </span>
          </span>
          
          <!-- Button Border Glow -->
          <div class="absolute inset-0 rounded-full bg-gradient-to-r from-blue-400 via-purple-400 to-indigo-400 opacity-0 group-hover:opacity-100 transition-opacity duration-300 blur-sm"></div>
        </button>
      </div>

      <!-- Testimonials Modal (Hidden by default) -->
      <div v-if="showModal" class="fixed inset-0 bg-black bg-opacity-50 flex items-center justify-center z-50 p-4"
        @click="closeModal">
        <div class="bg-white rounded-2xl p-8 max-w-4xl w-full max-h-[80vh] overflow-y-auto" @click.stop>
          <!-- Modal Header -->
          <div class="flex items-center justify-between mb-6">
            <h3 class="text-2xl font-bold text-gray-900">All Customer Testimonials</h3>
            <button @click="closeModal" class="text-gray-400 hover:text-gray-600 transition-colors duration-300">
              <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 18L18 6M6 6l12 12"></path>
              </svg>
            </button>
          </div>

          <!-- Extended Testimonials List -->
          <div class="grid grid-cols-1 md:grid-cols-2 gap-6">
            <div v-for="(testimonial, index) in extendedTestimonials" :key="index"
              class="bg-gray-50 rounded-xl p-6 border border-gray-200">
              <div class="text-3xl text-blue-500 mb-3">"</div>
              <p class="text-gray-700 leading-relaxed mb-4 italic text-sm">
                {{ testimonial.quote }}
              </p>
              <div class="flex items-center">
                <div
                  class="w-10 h-10 bg-gradient-to-br from-blue-500 to-purple-600 rounded-full flex items-center justify-center text-white font-bold text-sm mr-3">
                  {{ testimonial.avatar }}
                </div>
                <div>
                  <div class="font-semibold text-gray-900 text-sm">{{ testimonial.name }}</div>
                  <div class="text-xs text-gray-600">{{ testimonial.role }}</div>
                </div>
              </div>
            </div>
          </div>

          <!-- Modal Footer -->
          <div class="mt-8 text-center">
            <button 
              @click="closeModal"
              class="group relative inline-flex items-center justify-center px-6 py-3 text-base font-medium text-white bg-gradient-to-r from-gray-600 to-gray-700 rounded-lg shadow-md hover:shadow-lg transform hover:-translate-y-0.5 hover:scale-105 transition-all duration-300 ease-out overflow-hidden before:absolute before:inset-0 before:bg-gradient-to-r before:from-gray-700 before:to-gray-800 before:opacity-0 before:transition-opacity before:duration-300 hover:before:opacity-100"
            >
              <!-- Button Shine Effect -->
              <div class="absolute inset-0 bg-gradient-to-r from-transparent via-white/10 to-transparent -skew-x-12 -translate-x-full group-hover:translate-x-full transition-transform duration-700 ease-out"></div>
              
              <!-- Button Content -->
              <span class="relative z-10 flex items-center space-x-2">
                <svg class="w-4 h-4" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                  <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 18L18 6M6 6l12 12"></path>
                </svg>
                <span>Close</span>
              </span>
            </button>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import { ref } from 'vue'

// Reactive state
const isLoading = ref(false)
const showModal = ref(false)

// Testimonials data
const testimonials = [
  {
    quote: "Lorem ipsum dolor sit amet, consectetur adipiscing elit. Sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. This platform has completely transformed how we work.",
    name: "Sarah Johnson",
    role: "CEO, TechCorp",
    avatar: "S"
  },
  {
    quote: "Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. The performance improvements are incredible!",
    name: "Michael Chen",
    role: "Lead Developer",
    avatar: "M"
  },
  {
    quote: "Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Best decision we made for our business.",
    name: "Emily Rodriguez",
    role: "Product Manager",
    avatar: "E"
  }
]

// Extended testimonials for modal
const extendedTestimonials = [
  ...testimonials,
  {
    quote: "Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum. The customer support is outstanding!",
    name: "David Kim",
    role: "Marketing Director",
    avatar: "D"
  },
  {
    quote: "Sed ut perspiciatis unde omnis iste natus error sit voluptatem accusantium doloremque laudantium. This tool has increased our productivity by 300%.",
    name: "Lisa Wang",
    role: "Operations Manager",
    avatar: "L"
  },
  {
    quote: "Nemo enim ipsam voluptatem quia voluptas sit aspernatur aut odit aut fugit, sed quia consequuntur. Highly recommended for any business.",
    name: "James Wilson",
    role: "CTO",
    avatar: "J"
  },
  {
    quote: "At vero eos et accusamus et iusto odio dignissimos ducimus qui blanditiis praesentium voluptatum deleniti atque corrupti quos dolores.",
    name: "Maria Garcia",
    role: "Design Lead",
    avatar: "M"
  },
  {
    quote: "Temporibus autem quibusdam et aut officiis debitis aut rerum necessitatibus saepe eveniet ut et voluptates repudiandae sint et molestiae non recusandae.",
    name: "Alex Thompson",
    role: "Product Owner",
    avatar: "A"
  }
]

// Methods
const viewAllTestimonials = async () => {
  isLoading.value = true

  // Simulate API call delay
  await new Promise(resolve => setTimeout(resolve, 1000))

  isLoading.value = false
  showModal.value = true
}

const closeModal = () => {
  showModal.value = false
}
</script>

<style scoped>
/* Component-specific styles */
</style>
