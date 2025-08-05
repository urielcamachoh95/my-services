<template>
  <section class="py-16 bg-white px-4 sm:px-6 lg:px-8">
    <div class="container-custom">
      <div class="grid grid-cols-1 md:grid-cols-3 gap-8">
        <div
          v-for="(stat, index) in stats"
          :key="index"
          class="text-center"
          :ref="
            (el) => {
              if (el) statRefs[index] = el as HTMLElement
            }
          "
        >
          <div class="text-4xl font-bold text-black mb-2" :data-value="stat.value">
            <span class="counter">{{ stat.value }}</span>
          </div>
          <div class="text-gray-600">{{ stat.label }}</div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
import { ref, onMounted } from 'vue'
import { gsap } from 'gsap'
import { ScrollTrigger } from 'gsap/ScrollTrigger'

// Register ScrollTrigger plugin
gsap.registerPlugin(ScrollTrigger)

interface Stat {
  value: string
  label: string
}

interface Props {
  stats?: Stat[]
}

const props = withDefaults(defineProps<Props>(), {
  stats: () => [
    { value: '20+', label: 'Proyectos Completados' },
    { value: '24/7', label: 'Soporte Disponible' },
    { value: '7+', label: 'Años de Experiencia' },
  ],
})

const statRefs = ref<(HTMLElement | null)[]>([])

// Function to extract numeric value from string
const extractNumber = (value: string): number => {
  const match = value.match(/\d+/)
  return match ? parseInt(match[0]) : 0
}

// Function to animate counter
const animateCounter = (element: HTMLElement, targetValue: string) => {
  const numericValue = extractNumber(targetValue)
  const suffix = targetValue.replace(/\d+/, '') // Get the suffix (+, /, etc.)

  gsap.fromTo(
    element,
    { innerText: 0 },
    {
      innerText: numericValue,
      duration: 2,
      ease: 'power2.out',
      onUpdate: function () {
        element.innerText = Math.floor(this.targets()[0].innerText) + suffix
      },
      scrollTrigger: {
        trigger: element,
        start: 'top 80%',
        end: 'bottom 20%',
        toggleActions: 'play none none reverse',
      },
    },
  )
}

onMounted(() => {
  // Animate each counter when it enters viewport
  statRefs.value.forEach((ref, index) => {
    if (ref) {
      const counterElement = ref.querySelector('.counter') as HTMLElement
      if (counterElement) {
        animateCounter(counterElement, props.stats[index].value)
      }
    }
  })
})

defineExpose({
  statRefs,
})
</script>
