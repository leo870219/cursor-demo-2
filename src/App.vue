<script setup>
import TestimonialCard from './components/TestimonialCard.vue'
import { testimonials } from './data/testimonials.js'
</script>

<template>
  <main class="container">
    <div class="testimonial-grid">
      <TestimonialCard
        v-for="testimonial in testimonials"
        :key="testimonial.id"
        :testimonial="testimonial"
      />
    </div>
  </main>
</template>

<style>
body {
  background-color: #f3f4f6;
  min-height: 100vh;
  margin: 0;
  padding: 2rem;
}

.container {
  max-width: 1280px;
  margin: 0 auto;
}

.testimonial-grid {
  display: grid;
  gap: 2rem;
  grid-template-columns: repeat(1, 1fr);
  padding: 1rem;
}

@media (min-width: 768px) {
  .testimonial-grid {
    grid-template-columns: repeat(2, 1fr);
  }
}

@media (min-width: 1024px) {
  .testimonial-grid {
    grid-template-columns: repeat(3, 1fr);
  }
}
</style>
