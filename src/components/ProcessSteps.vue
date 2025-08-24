<template>
  <section class="vapor-section-alt glass-section-alt">
    <div class="vapor-section-content">
      <div class="vapor-section-header">
        <h2 class="vapor-section-title vapor-fade-in" ref="processTitle">
          {{ title }}
        </h2>
        <p class="vapor-section-subtitle vapor-fade-in">
          {{ subtitle }}
        </p>
      </div>

      <!-- Process Steps Grid -->
      <div class="vapor-grid-normal grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4">
        <ProcessStep
          v-for="step in allSteps"
          :key="step.stepNumber"
          :step-number="step.stepNumber"
          :title="step.title"
          :description="step.description"
          :items="step.items"
          :icon="step.icon"
          :variant="step.variant"
          ref="stepRefs"
        />
      </div>

      <!-- Mobile Process Steps Carousel -->
      <div class="md:hidden relative overflow-hidden mt-6" ref="mobileProcessCarousel">
        <div
          class="flex transition-transform duration-500 ease-out mobile-carousel-track slide-0"
          ref="mobileProcessTrack"
          @touchstart="handleProcessTouchStart"
          @touchend="handleProcessTouchEnd"
        >
          <div
            v-for="step in allSteps"
            :key="step.stepNumber"
            class="w-full flex-shrink-0 px-4"
            :style="{ width: '100%' }"
          >
            <div
              class="glass-card relative overflow-hidden h-full p-5 hover:shadow-lg hover:-translate-y-1 transition-all duration-300"
            >
              <!-- Step number -->
              <div class="absolute top-4 right-4 text-6xl font-bold text-slate-200/60">
                {{ step.stepNumber.toString().padStart(2, '0') }}
              </div>

              <!-- Icon and title -->
              <div class="flex items-center justify-between mb-4">
                <div
                  :class="`w-16 h-16 ${getIconBackground(step.variant)} rounded-2xl flex items-center justify-center`"
                >
                  <component :is="step.icon" class="w-8 h-8 text-white" />
                </div>
              </div>

              <!-- Content -->
              <div class="space-y-3">
                <h3 class="text-xl font-semibold text-slate-800">{{ step.title }}</h3>
                <p class="text-slate-600 leading-relaxed">{{ step.description }}</p>
                <div class="space-y-2 pt-3">
                  <div
                    v-for="(item, index) in step.items"
                    :key="index"
                    class="flex items-center gap-3 text-base text-gray-500 group-hover:text-gray-700 transition-all duration-300 group/item"
                  >
                    <div
                      :class="`w-2 h-2 ${getDotColor(step.variant)} rounded-full flex-shrink-0`"
                    ></div>
                    <span>{{ item }}</span>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>

        <!-- Mobile Navigation -->
        <button
          @click="previousProcessStep"
          class="absolute left-2 top-1/2 transform -translate-y-1/2 w-10 h-10 bg-white/90 backdrop-blur-sm rounded-full shadow-lg border border-slate-200 flex items-center justify-center hover:bg-cyan-50 transition-colors duration-300 z-10"
          :disabled="currentProcessStep === 0"
        >
          <svg class="w-5 h-5 text-slate-600" fill="none" stroke="currentColor" viewBox="0 0 24 24">
            <path
              stroke-linecap="round"
              stroke-linejoin="round"
              stroke-width="2"
              d="M15 19l-7-7 7-7"
            />
          </svg>
        </button>

        <button
          @click="nextProcessStep"
          class="absolute right-2 top-1/2 transform -translate-y-1/2 w-10 h-10 bg-white/90 backdrop-blur-sm rounded-full shadow-lg border border-slate-200 flex items-center justify-center hover:bg-cyan-50 transition-colors duration-300 z-10"
          :disabled="currentProcessStep === allSteps.length - 1"
        >
          <svg class="w-5 h-5 text-slate-600" fill="none" stroke="currentColor" viewBox="0 0 24 24">
            <path
              stroke-linecap="round"
              stroke-linejoin="round"
              stroke-width="2"
              d="M9 5l7 7-7 7"
            />
          </svg>
        </button>

        <!-- Mobile Dots -->
        <div class="flex justify-center mt-4 space-x-2">
          <button
            v-for="(step, index) in allSteps"
            :key="index"
            @click="goToProcessStep(index)"
            class="w-2 h-2 rounded-full transition-all duration-300"
            :class="currentProcessStep === index ? 'bg-cyan-500 w-6' : 'bg-slate-300'"
          ></button>
        </div>
      </div>

      <!-- Enhanced CTA section with glassmorphism design -->
      <div class="relative vapor-section-margin-tight">
        <div class="text-center">
          <div class="flex flex-col sm:flex-row gap-4 justify-center">
            <a href="#servicios" class="vapor-btn-primary text-lg group">
              Ver servicios
              <svg
                class="w-5 h-5 group-hover:translate-x-1 transition-transform duration-300"
                fill="none"
                stroke="currentColor"
                viewBox="0 0 24 24"
              >
                <path
                  stroke-linecap="round"
                  stroke-linejoin="round"
                  stroke-width="2"
                  d="M10 6H6a2 2 0 00-2 2v10a2 2 0 002 2h10a2 2 0 002-2v-4M14 4h6m0 0v6m0-6L10 14"
                ></path>
              </svg>
            </a>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
import { ref, computed, onMounted } from 'vue'
import { MessageSquare, ClipboardList, Code, Zap } from 'lucide-vue-next'
import ProcessStep from './ProcessStep.vue'

interface Props {
  title?: string
  subtitle?: string
}

withDefaults(defineProps<Props>(), {
  title: '¿Cómo trabajo?',
  subtitle: 'Mi proceso de desarrollo web, paso a paso',
})

const processTitle = ref<HTMLElement>()
const stepRefs = ref<HTMLElement[]>([])

// Mobile process carousel refs
const mobileProcessCarousel = ref<HTMLElement>()
const mobileProcessTrack = ref<HTMLElement>()
const currentProcessStep = ref(0)

// Process steps data
const allSteps = computed(() => [
  {
    stepNumber: '01',
    title: 'Conversamos',
    description:
      'Platicamos sobre tu negocio, objetivos y lo que realmente necesitas para avanzar.',
    items: [
      'Entrevista inicial sin compromiso',
      'Análisis de necesidades específicas',
      'Definición clara del alcance',
    ],
    icon: MessageSquare,
    variant: 'primary' as const,
  },
  {
    stepNumber: '02',
    title: 'Planificamos',
    description:
      'Te presento una propuesta clara con timeline realista y presupuesto transparente.',
    items: [
      'Propuesta técnica detallada',
      'Timeline con hitos claros',
      'Presupuesto sin sorpresas',
    ],
    icon: ClipboardList,
    variant: 'accent' as const,
  },
  {
    stepNumber: '03',
    title: 'Construimos',
    description:
      'Desarrollo tu proyecto con código limpio, pruebas continuas y feedback constante.',
    items: [
      'Desarrollo iterativo y transparente',
      'Testing continuo de funcionalidades',
      'Comunicación regular del progreso',
    ],
    icon: Code,
    variant: 'success' as const,
  },
  {
    stepNumber: '04',
    title: 'Entregamos',
    description: 'Despliego tu proyecto de forma segura y te entrego todo listo para usar.',
    items: [
      'Despliegue seguro y optimizado',
      'Configuración completa del sistema',
      'Documentación clara y videos tutoriales',
    ],
    icon: Zap,
    variant: 'mixed' as const,
  },
])

// Mobile carousel functions
const nextProcessStep = () => {
  if (currentProcessStep.value < allSteps.value.length - 1) {
    currentProcessStep.value++
    animateProcessStep()
  }
}

const previousProcessStep = () => {
  if (currentProcessStep.value > 0) {
    currentProcessStep.value--
    animateProcessStep()
  }
}

const goToProcessStep = (index: number) => {
  currentProcessStep.value = index
  animateProcessStep()
}

const animateProcessStep = () => {
  if (mobileProcessTrack.value) {
    // Remove all slide classes first
    mobileProcessTrack.value.classList.remove('slide-0', 'slide-1', 'slide-2', 'slide-3')
    // Add the current slide class
    mobileProcessTrack.value.classList.add(`slide-${currentProcessStep.value}`)
  }
}

// Touch interactions for mobile carousel
let processTouchStartX = 0
let processTouchEndX = 0

const handleProcessTouchStart = (e: TouchEvent) => {
  processTouchStartX = e.changedTouches[0].screenX
}

const handleProcessTouchEnd = (e: TouchEvent) => {
  processTouchEndX = e.changedTouches[0].screenX
  handleProcessSwipe()
}

const handleProcessSwipe = () => {
  const swipeThreshold = 50
  const diff = processTouchStartX - processTouchEndX

  if (Math.abs(diff) > swipeThreshold) {
    if (diff > 0 && currentProcessStep.value < allSteps.value.length - 1) {
      // Swipe left - next
      nextProcessStep()
    } else if (diff < 0 && currentProcessStep.value > 0) {
      // Swipe right - previous
      previousProcessStep()
    }
  }
}

// Helper functions for styling
const getIconBackground = (variant: string) => {
  switch (variant) {
    case 'primary':
      return 'bg-cyan-500'
    case 'secondary':
      return 'bg-sky-500'
    case 'success':
      return 'bg-emerald-500'
    case 'accent':
      return 'bg-violet-500'
    default:
      return 'bg-cyan-500'
  }
}

const getDotColor = (variant: string) => {
  switch (variant) {
    case 'primary':
      return 'bg-cyan-500'
    case 'secondary':
      return 'bg-sky-500'
    case 'success':
      return 'bg-emerald-500'
    case 'accent':
      return 'bg-violet-500'
    default:
      return 'bg-cyan-500'
  }
}

onMounted(() => {
  // Initialize mobile carousel
  if (mobileProcessTrack.value) {
    // Set initial position
    currentProcessStep.value = 0
  }
})

defineExpose({
  processTitle,
  stepRefs,
})
</script>
