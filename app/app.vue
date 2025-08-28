<template>
  <div>
    <!-- Navigation -->
    <Navigation />

    <!-- Main Content -->
    <main class="pt-16">
      <!-- Hero Section -->
      <HeroSection />

      <!-- Features Section -->
      <section id="features">
        <FeaturesSection />
      </section>

      <!-- About Section -->
      <section id="about">
        <AboutSection />
      </section>

      <!-- Testimonials Section -->
      <section id="testimonials">
        <TestimonialsSection />
      </section>

      <!-- Pricing Section -->
      <section id="pricing">
        <PricingSection />
      </section>

      <!-- Footer Section -->
      <FooterSection />
    </main>
  </div>
</template>

<script setup>
// Explicit component imports
import Navigation from '../components/Navigation.vue'
import HeroSection from '../components/HeroSection.vue'
import FeaturesSection from '../components/FeaturesSection.vue'
import AboutSection from '../components/AboutSection.vue'
import TestimonialsSection from '../components/TestimonialsSection.vue'
import PricingSection from '../components/PricingSection.vue'
import FooterSection from '../components/FooterSection.vue'
</script>

<style>
/* Global styles are handled in assets/css/main.css */
</style>
