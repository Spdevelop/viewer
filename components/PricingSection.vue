<template>
  <section class="section-padding bg-gray-50 py-24 p-10">
    <div class="container-custom">
      <!-- Section Header -->
      <div class="text-center mb-20 animate-fade-in-up mt-8">
        <h2 class="text-4xl md:text-5xl font-bold mb-6 text-gradient">
          Choose Your Plan
        </h2>
        <p class="text-xl text-gray-600 max-w-2xl mx-auto">
          Start with our free plan and scale as you grow
        </p>
      </div>

      <!-- Pricing Cards -->
      <div class="grid grid-cols-1 md:grid-cols-3 gap-8 max-w-6xl mx-auto mb-16">
        <div v-for="(plan, index) in plans" :key="index" class="relative group animate-fade-in-up"
          :style="{ animationDelay: `${index * 200}ms` }">
          <!-- Popular Badge -->
          <div v-if="plan.popular"
            class="absolute -top-6 left-1/2 transform -translate-x-1/2 bg-gradient-to-r from-blue-600 to-purple-600 text-white px-6 py-2 rounded-full text-sm font-semibold shadow-lg z-10">
            Most Popular
          </div>

          <!-- Card -->
          <div
            class="bg-white mt-10 rounded-2xl p-8 shadow-lg hover:shadow-2xl transition-all duration-500 transform hover:-translate-y-2 hover:scale-105 border-2 mt-4"
            :class="plan.popular ? 'border-blue-500' : 'border-gray-100'">
            <!-- Plan Name -->
            <h3 class="text-2xl font-bold text-gray-900 mb-4">{{ plan.name }}</h3>

            <!-- Price -->
            <div class="mb-6">
              <span class="text-4xl font-bold text-gray-900">${{ plan.price }}</span>
              <span class="text-gray-600 ml-2">{{ plan.period }}</span>
            </div>

            <!-- Description -->
            <p class="text-gray-600 mb-8">{{ plan.description }}</p>

            <!-- Features List -->
            <ul class="space-y-4 mb-8">
              <li v-for="feature in plan.features" :key="feature" class="flex items-center">
                <div class="w-5 h-5 bg-green-500 rounded-full flex items-center justify-center mr-3 flex-shrink-0">
                  <svg class="w-3 h-3 text-white" fill="currentColor" viewBox="0 0 20 20">
                    <path fill-rule="evenodd"
                      d="M16.707 5.293a1 1 0 010 1.414l-8 8a1 1 0 01-1.414 0l-4-4a1 1 0 011.414-1.414L8 12.586l7.293-7.293a1 1 0 011.414 0z"
                      clip-rule="evenodd"></path>
                  </svg>
                </div>
                <span class="text-gray-700">{{ feature }}</span>
              </li>
            </ul>

            <!-- CTA Button -->
            <button
              class="w-full py-3 px-6 rounded-full font-semibold transition-all duration-300 transform hover:scale-105"
              :class="plan.popular ? 'btn-primary' : 'btn-secondary'">
              {{ plan.buttonText }}
            </button>
          </div>
        </div>
      </div>

      <!-- Additional Info -->
      <div class="text-center mt-16 animate-fade-in-up" style="animation-delay: 800ms;">
        <p class="text-gray-600 mb-4">
          All plans include 14-day money-back guarantee
        </p>
        <p class="text-gray-600">
          Need a custom plan? <a href="#" class="text-blue-600 hover:text-blue-700 font-semibold">Contact us</a>
        </p>
      </div>
    </div>
  </section>
</template>

<script setup>
// Pricing plans data
const plans = [
  {
    name: "Basic",
    price: "0",
    period: "/month",
    description: "Perfect for getting started and small projects",
    features: [
      "Up to 3 projects",
      "Basic analytics",
      "Community support",
      "1GB storage",
      "Basic templates"
    ],
    buttonText: "Get Started Free",
    popular: false
  },
  {
    name: "Pro",
    price: "29",
    period: "/month",
    description: "Ideal for growing businesses and teams",
    features: [
      "Up to 25 projects",
      "Advanced analytics",
      "Priority support",
      "10GB storage",
      "Premium templates",
      "Team collaboration",
      "API access"
    ],
    buttonText: "Start Pro Trial",
    popular: true
  },
  {
    name: "Enterprise",
    price: "99",
    period: "/month",
    description: "For large organizations with advanced needs",
    features: [
      "Unlimited projects",
      "Custom analytics",
      "24/7 phone support",
      "Unlimited storage",
      "Custom templates",
      "Advanced security",
      "Dedicated account manager",
      "Custom integrations"
    ],
    buttonText: "Contact Sales",
    popular: false
  }
]
</script>

<style scoped>
/* Component-specific styles */
</style>
