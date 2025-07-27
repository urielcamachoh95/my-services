<template>
  <div class="max-w-6xl mx-auto">
    <h2 class="text-4xl md:text-5xl font-bold text-black text-center mb-20" ref="testimonialsTitle">
      {{ title }}
    </h2>

    <div class="grid md:grid-cols-2 gap-12">
      <TestimonialCard
        v-for="(testimonial, index) in testimonials"
        :key="index"
        :quote="testimonial.quote"
        :author-name="testimonial.authorName"
        :author-title="testimonial.authorTitle"
        :avatar-emoji="testimonial.avatarEmoji"
        :variant="testimonial.variant"
        ref="testimonialRefs"
      />
    </div>
  </div>
</template>

<script setup lang="ts">
import { ref, computed } from 'vue'
import TestimonialCard from './TestimonialCard.vue'

interface Props {
  title?: string
}

withDefaults(defineProps<Props>(), {
  title: 'Lo que dicen mis clientes',
})

const testimonialsTitle = ref<HTMLElement>()
const testimonialRefs = ref<HTMLElement[]>([])
const testimonialStats = ref<HTMLElement>()

// Testimonials data
const testimonials = computed(() => [
  {
    quote:
      'Uriel nos ayudó a lanzar nuestro sitio después de mucho tiempo posponiéndolo. Ahora recibimos reservaciones sin depender de mensajes o llamadas todo el día. Fue claro y comprometido desde el inicio.',
    authorName: 'Cabañas en Atlixco',
    authorTitle: 'Dueña de cabañas rurales en Atlixco',
    avatarEmoji: '🌲',
    variant: 'primary' as const,
  },
  {
    quote:
      'Gracias al nuevo sitio en Shopify ahora nuestros clientes pueden ver todo el catálogo desde cualquier lugar. Todo el proceso fue ágil y profesional, entendió justo lo que necesitábamos.',
    authorName: 'Renta de mobiliario y flores en Puebla',
    authorTitle: 'Fundadora de tienda de renta y flores en Puebla',
    avatarEmoji: '🌸',
    variant: 'accent' as const,
  },
])

defineExpose({
  testimonialsTitle,
  testimonialRefs,
  testimonialStats,
})
</script>
