<script setup>
import StarRating from './StarRating.vue'

defineProps({
  testimonial: {
    type: Object,
    required: true,
    validator: (value) => {
      return (
        value.rating &&
        value.content &&
        value.author &&
        value.author.name &&
        value.author.title &&
        value.author.avatar
      )
    },
  },
})
</script>

<template>
  <div class="testimonial-card">
    <StarRating :rating="testimonial.rating" />
    <p class="content">{{ testimonial.content }}</p>
    <div class="author">
      <img :src="testimonial.author.avatar" :alt="testimonial.author.name" class="avatar" />
      <div class="author-info">
        <h3 class="name">{{ testimonial.author.name }}</h3>
        <p class="title">{{ testimonial.author.title }}</p>
      </div>
    </div>
  </div>
</template>

<style scoped>
.testimonial-card {
  padding: 2rem;
  background: white;
  border-radius: 0.5rem;
  box-shadow: 0 1px 3px rgba(0, 0, 0, 0.1);
}

.content {
  margin: 1rem 0;
  color: #374151;
  line-height: 1.5;
}

.author {
  display: flex;
  align-items: center;
  gap: 1rem;
}

.avatar {
  width: 2.5rem;
  height: 2.5rem;
  border-radius: 9999px;
  object-fit: cover;
}

.author-info {
  display: flex;
  flex-direction: column;
}

.name {
  font-weight: 500;
  color: #111827;
}

.title {
  color: #6b7280;
  font-size: 0.875rem;
}
</style>
