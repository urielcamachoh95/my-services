<template>
  <div class="max-w-6xl mx-auto">
    <h2
      class="text-4xl md:text-5xl font-bold text-slate-800 text-center mb-16"
      ref="testimonialsTitle"
    >
      {{ title }}
    </h2>

    <!-- Testimonials Carousel -->
    <div class="relative overflow-hidden" ref="carouselContainer">
      <div class="flex transition-transform duration-500 ease-out" ref="testimonialsTrack">
        <div
          v-for="(slide, slideIndex) in testimonialSlides"
          :key="slideIndex"
          class="w-full flex-shrink-0 px-4"
          :style="{ width: '100%' }"
        >
          <div class="grid grid-cols-1 md:grid-cols-2 gap-6 md:gap-8 lg:gap-12">
            <div
              v-for="(testimonial, testimonialIndex) in slide"
              :key="`${slideIndex}-${testimonialIndex}`"
              class="glass-card p-6 hover:shadow-lg hover:-translate-y-1 transition-all duration-300"
              ref="testimonialRefs"
            >
              <!-- Quote icon -->
              <div class="flex justify-between items-start mb-4">
                <div class="w-12 h-12 bg-cyan-100 rounded-full flex items-center justify-center">
                  <svg class="w-6 h-6 text-cyan-600" fill="currentColor" viewBox="0 0 24 24">
                    <path
                      d="M14.017 21v-7.391c0-5.704 3.731-9.57 8.983-10.609l.995 2.151c-2.432.917-3.995 3.638-3.995 5.849h4v10h-9.983zm-14.017 0v-7.391c0-5.704 3.748-9.57 9-10.609l.996 2.151c-2.433.917-3.996 3.638-3.996 5.849h3.983v10h-9.983z"
                    />
                  </svg>
                </div>
                <div class="w-6 h-6 bg-cyan-100 rounded-full flex items-center justify-center">
                  <svg class="w-3 h-3 text-cyan-600" fill="currentColor" viewBox="0 0 24 24">
                    <path d="M9 12l2 2 4-4m6 2a9 9 0 11-18 0 9 9 0 0118 0z" />
                  </svg>
                </div>
              </div>

              <!-- Testimonial text -->
              <blockquote class="text-slate-700 text-lg leading-relaxed mb-6">
                "{{ testimonial.quote }}"
              </blockquote>

              <!-- Author info -->
              <div class="flex items-center gap-3">
                <div
                  class="w-10 h-10 bg-cyan-100 rounded-full flex items-center justify-center text-lg"
                >
                  {{ testimonial.avatarEmoji }}
                </div>
                <div>
                  <div class="font-semibold text-slate-800">{{ testimonial.authorName }}</div>
                  <div class="text-sm text-slate-600">{{ testimonial.authorTitle }}</div>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>

      <!-- Navigation Arrows -->
      <button
        @click="previousSlide"
        class="carousel-arrow absolute left-4 top-1/2 transform -translate-y-1/2 z-10"
        :disabled="currentSlide === 0"
      >
        <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24">
          <path
            stroke-linecap="round"
            stroke-linejoin="round"
            stroke-width="2"
            d="M15 19l-7-7 7-7"
          />
        </svg>
      </button>

      <button
        @click="nextSlide"
        class="carousel-arrow absolute right-4 top-1/2 transform -translate-y-1/2 z-10"
        :disabled="currentSlide === testimonialSlides.length - 1"
      >
        <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24">
          <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 5l7 7-7 7" />
        </svg>
      </button>

      <!-- Navigation Dots -->
      <div class="flex justify-center mt-8 space-x-2">
        <button
          v-for="(slide, index) in testimonialSlides"
          :key="index"
          @click="goToSlide(index)"
          class="carousel-dot"
          :class="{ active: index === currentSlide }"
        ></button>
      </div>

      <!-- Auto-play Toggle -->
      <div class="flex justify-center mt-4">
        <button
          @click="toggleAutoPlay"
          class="auto-play-toggle"
          :class="{ playing: isAutoPlaying }"
        >
          <svg v-if="!isAutoPlaying" class="w-4 h-4" fill="currentColor" viewBox="0 0 24 24">
            <path d="M8 5v14l11-7z" />
          </svg>
          <svg v-else class="w-4 h-4" fill="currentColor" viewBox="0 0 24 24">
            <path d="M6 19h4V5H6v14zm8-14v14h4V5h-4z" />
          </svg>
        </button>
      </div>
    </div>

    <!-- Stats Section -->
    <div
      class="testimonials-stats mt-16 grid grid-cols-1 md:grid-cols-3 gap-8"
      ref="testimonialStats"
    >
      <div
        class="glass-card text-center p-6 hover:shadow-lg hover:-translate-y-1 transition-all duration-300"
      >
        <div class="text-3xl font-bold text-cyan-600 mb-2">100%</div>
        <div class="text-xs text-slate-600">Clientes Satisfechos</div>
      </div>
      <div
        class="glass-card text-center p-6 hover:shadow-lg hover:-translate-y-1 transition-all duration-300"
      >
        <div class="text-3xl font-bold text-sky-600 mb-2">20+</div>
        <div class="text-xs text-slate-600">Proyectos Exitosos</div>
      </div>
      <div
        class="glass-card text-center p-6 hover:shadow-lg hover:-translate-y-1 transition-all duration-300"
      >
        <div class="text-3xl font-bold text-violet-600 mb-2">4.9/5</div>
        <div class="text-xs text-slate-600">Calificación Promedio</div>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
import { ref, computed, onMounted, onUnmounted, nextTick } from 'vue'
import { gsap } from 'gsap'

interface Props {
  title?: string
}

withDefaults(defineProps<Props>(), {
  title: 'Lo que dicen mis clientes',
})

const testimonialsTitle = ref<HTMLElement>()
const testimonialRefs = ref<HTMLElement[]>([])
const testimonialStats = ref<HTMLElement>()

// Carousel state
const currentSlide = ref(0)
const testimonialSlides = computed(() => {
  const slides: any[][] = []
  for (let i = 0; i < testimonials.value.length; i += 2) {
    slides.push(testimonials.value.slice(i, i + 2))
  }
  return slides
})
const carouselContainer = ref<HTMLElement>()
const testimonialsTrack = ref<HTMLElement>()
const isAutoPlaying = ref(true)
let autoPlayInterval: number | null = null

// Testimonials data
const testimonials = computed(() => [
  {
    quote:
      'Uriel nos ayudó a lanzar nuestro sitio después de mucho tiempo posponiéndolo. Ahora recibimos reservaciones sin depender de mensajes o llamadas todo el día. Fue claro y comprometido desde el inicio.',
    authorName: 'Cabañas en Atlixco',
    authorTitle: 'Dueño de cabañas en Atlixco',
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
  {
    quote:
      'Uriel transformó completamente nuestra presencia digital. El sitio web que creó no solo se ve profesional, sino que también ha aumentado nuestras ventas en línea significativamente.',
    authorName: 'Restaurante Tradicional Mexicano',
    authorTitle: 'Propietario de restaurante en Puebla',
    avatarEmoji: '🍽️',
    variant: 'primary' as const,
  },
  {
    quote:
      'Excelente trabajo en nuestro e-commerce. Uriel entendió perfectamente nuestro modelo de negocio y creó una solución que se adapta perfectamente a nuestras necesidades.',
    authorName: 'Tienda de Artesanías',
    authorTitle: 'Emprendedora en artesanías mexicanas',
    avatarEmoji: '🎨',
    variant: 'accent' as const,
  },
])

// GSAP animations
const animateToIndex = (index: number) => {
  if (!testimonialsTrack.value) return

  const translateX = -index * 100

  // Animate track movement with bounce effect
  gsap.to(testimonialsTrack.value, {
    x: `${translateX}%`,
    duration: 1.2,
    ease: 'power2.out',
  })

  // Animate current slide testimonials in with enhanced effects
  const currentSlideTestimonials = testimonialRefs.value.slice(index * 2, (index + 1) * 2)
  currentSlideTestimonials.forEach((testimonial, testimonialIndex) => {
    gsap.fromTo(
      testimonial,
      {
        opacity: 0,
        y: 30,
        scale: 0.9,
        rotationY: -15,
      },
      {
        opacity: 1,
        y: 0,
        scale: 1,
        rotationY: 0,
        duration: 0.8,
        ease: 'back.out(1.7)',
        delay: 0.3 + testimonialIndex * 0.1, // Stagger testimonials within slide
      },
    )
  })

  // Animate previous slide testimonials out
  if (currentSlide.value !== index) {
    const previousSlideTestimonials = testimonialRefs.value.slice(
      currentSlide.value * 2,
      (currentSlide.value + 1) * 2,
    )
    previousSlideTestimonials.forEach((testimonial) => {
      gsap.to(testimonial, {
        opacity: 0.6,
        scale: 0.95,
        y: -10,
        duration: 0.5,
        ease: 'power2.out',
      })
    })
  }

  // Animate dots with stagger effect
  gsap.to('.carousel-dot', {
    scale: 1,
    duration: 0.3,
    ease: 'power2.out',
  })

  gsap.to(`.carousel-dot:nth-child(${index + 1})`, {
    scale: 1.25,
    duration: 0.4,
    ease: 'back.out(1.7)',
    delay: 0.1,
  })

  // Animate navigation arrows
  gsap.to('.carousel-arrow', {
    scale: 1,
    duration: 0.3,
    ease: 'power2.out',
  })

  currentSlide.value = index
}

// Enhanced entrance animation for testimonials
const animateTestimonialsEntrance = () => {
  if (!testimonialRefs.value.length) return

  // Set initial state for all testimonials
  gsap.set(testimonialRefs.value, {
    opacity: 0,
    y: 50,
    scale: 0.8,
  })

  // Animate first slide testimonials in
  const firstSlideTestimonials = testimonialRefs.value.slice(0, 2)
  firstSlideTestimonials.forEach((testimonial, index) => {
    gsap.to(testimonial, {
      opacity: 1,
      y: 0,
      scale: 1,
      duration: 1,
      ease: 'back.out(1.7)',
      delay: 0.2 + index * 0.2, // Stagger first slide testimonials
    })
  })

  // Stagger animate other slide testimonials
  const otherTestimonials = testimonialRefs.value.slice(2)
  gsap.to(otherTestimonials, {
    opacity: 0.7,
    y: 0,
    scale: 0.95,
    duration: 0.8,
    ease: 'power2.out',
    stagger: 0.1,
    delay: 0.8,
  })

  // Animate stats section with delay
  gsap.fromTo(
    '.testimonials-stats',
    {
      opacity: 0,
      y: 30,
    },
    {
      opacity: 1,
      y: 0,
      duration: 0.8,
      ease: 'power2.out',
      delay: 1.5,
    },
  )

  // Stagger animate individual stat cards
  gsap.fromTo(
    '.testimonials-stats > div',
    {
      opacity: 0,
      y: 20,
      scale: 0.9,
    },
    {
      opacity: 1,
      y: 0,
      scale: 1,
      duration: 0.6,
      ease: 'back.out(1.7)',
      stagger: 0.15,
      delay: 1.8,
    },
  )
}

// Navigation functions
const nextSlide = () => {
  if (currentSlide.value < testimonialSlides.value.length - 1) {
    animateToIndex(currentSlide.value + 1)
  }
}

const previousSlide = () => {
  if (currentSlide.value > 0) {
    animateToIndex(currentSlide.value - 1)
  }
}

const goToSlide = (index: number) => {
  animateToIndex(index)
}

// Auto-play functionality
const startAutoPlay = () => {
  if (autoPlayInterval) return

  autoPlayInterval = window.setInterval(() => {
    if (currentSlide.value < testimonialSlides.value.length - 1) {
      nextSlide()
    } else {
      animateToIndex(0) // Loop back to first
    }
  }, 5000) // Change every 5 seconds
}

const stopAutoPlay = () => {
  if (autoPlayInterval) {
    clearInterval(autoPlayInterval)
    autoPlayInterval = null
  }
}

const toggleAutoPlay = () => {
  isAutoPlaying.value = !isAutoPlaying.value
  if (isAutoPlaying.value) {
    startAutoPlay()
  } else {
    stopAutoPlay()
  }
}

// Keyboard navigation
const handleKeyboardNavigation = (event: KeyboardEvent) => {
  switch (event.key) {
    case 'ArrowLeft':
      event.preventDefault()
      previousSlide()
      break
    case 'ArrowRight':
      event.preventDefault()
      nextSlide()
      break
    case ' ':
      event.preventDefault()
      toggleAutoPlay()
      break
  }
}

// Lifecycle
onMounted(() => {
  // Wait for next tick to ensure DOM is ready
  nextTick(() => {
    // Initialize enhanced entrance animation
    animateTestimonialsEntrance()

    // Start auto-play after entrance animation
    if (isAutoPlaying.value) {
      setTimeout(() => {
        startAutoPlay()
      }, 2000) // Start auto-play after 2 seconds
    }
  })

  // Pause auto-play on hover
  if (carouselContainer.value) {
    carouselContainer.value.addEventListener('mouseenter', stopAutoPlay)
    carouselContainer.value.addEventListener('mouseleave', () => {
      if (isAutoPlaying.value) {
        startAutoPlay()
      }
    })
  }

  // Add keyboard navigation
  document.addEventListener('keydown', handleKeyboardNavigation)
})

onUnmounted(() => {
  stopAutoPlay()
  if (carouselContainer.value) {
    carouselContainer.value.removeEventListener('mouseenter', stopAutoPlay)
    carouselContainer.value.removeEventListener('mouseleave', startAutoPlay)
  }
  document.removeEventListener('keydown', handleKeyboardNavigation)
})

defineExpose({
  testimonialsTitle,
  testimonialRefs,
  testimonialStats,
})
</script>

<style scoped>
/* Custom scrollbar for webkit browsers */
.testimonials-track::-webkit-scrollbar {
  display: none;
}

.testimonials-track {
  -ms-overflow-style: none;
  scrollbar-width: none;
}
</style>
