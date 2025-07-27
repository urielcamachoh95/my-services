<template>
  <div class="max-w-6xl mx-auto px-4">
    <!-- Header section -->
    <div class="text-center mb-16" ref="processTitle">
      <h2 class="text-3xl md:text-4xl lg:text-5xl font-bold text-black mb-4">
        {{ title }}
      </h2>
      <p class="text-gray-600 text-lg max-w-2xl mx-auto">
        Un proceso simple y efectivo para llevar tu proyecto al siguiente nivel
      </p>
    </div>

    <!-- Progress line -->
    <div class="relative mb-12 md:mb-16">
      <div class="absolute top-6 left-0 right-0 h-1 bg-gray-300 rounded-full"></div>
      <div
        class="absolute top-6 left-0 h-1 bg-black rounded-full transition-all duration-1000 shadow-sm"
        :style="{ width: `${(currentProcessStep + 1) * 20}%` }"
        ref="progressLine"
      ></div>
    </div>

    <!-- First Row: Steps 1-3 -->
    <div class="grid md:grid-cols-2 lg:grid-cols-3 gap-6 md:gap-8 mb-8 md:mb-12 relative">
      <!-- Connecting line for first row -->
      <div
        class="hidden lg:block absolute top-1/2 left-1/4 right-1/4 h-0.5 bg-gray-300 transform -translate-y-1/2 z-0"
      ></div>

      <ProcessStep
        v-for="(step, index) in firstRowSteps"
        :key="index"
        :step-number="step.stepNumber"
        :title="step.title"
        :description="step.description"
        :items="step.items"
        :icon="step.icon"
        :variant="step.variant"
        ref="firstRowRefs"
      />
    </div>

    <!-- Vertical connecting line between rows -->
    <div
      class="hidden lg:block absolute left-1/2 top-1/2 w-0.5 h-8 bg-gray-300 transform -translate-x-1/2 z-0"
    ></div>

    <!-- Second Row: Steps 4-5 -->
    <div
      class="grid md:grid-cols-2 lg:grid-cols-2 gap-6 md:gap-8 justify-items-center relative max-w-4xl mx-auto"
    >
      <!-- Connecting line for second row -->
      <div
        class="hidden lg:block absolute top-1/2 left-1/3 right-1/3 h-0.5 bg-gray-300 transform -translate-y-1/2 z-0"
      ></div>

      <ProcessStep
        v-for="(step, index) in secondRowSteps"
        :key="index + 3"
        :step-number="step.stepNumber"
        :title="step.title"
        :description="step.description"
        :items="step.items"
        :icon="step.icon"
        :variant="step.variant"
        ref="secondRowRefs"
      />
    </div>
  </div>
</template>

<script setup lang="ts">
import { ref, computed } from 'vue'
import ProcessStep from './ProcessStep.vue'
import ChatIcon from './icons/ChatIcon.vue'
import ClipboardIcon from './icons/ClipboardIcon.vue'
import CodeIcon from './icons/CodeIcon.vue'
import LightningIcon from './icons/LightningIcon.vue'
import CogIcon from './icons/CogIcon.vue'

interface Props {
  title?: string
}

withDefaults(defineProps<Props>(), {
  title: '¿Cómo trabajo?',
})

const currentProcessStep = ref(0)
const processTitle = ref<HTMLElement>()
const progressLine = ref<HTMLElement>()
const firstRowRefs = ref<HTMLElement[]>([])
const secondRowRefs = ref<HTMLElement[]>([])

// Process steps data
const firstRowSteps = computed(() => [
  {
    stepNumber: '01',
    title: 'Descubrimiento',
    description: 'Entiendo tu visión y objetivos para crear la estrategia perfecta.',
    items: ['Entrevista inicial', 'Análisis de necesidades', 'Plan estratégico'],
    icon: ChatIcon,
    variant: 'primary' as const,
  },
  {
    stepNumber: '02',
    title: 'Planificación',
    description: 'Propuesta clara con timeline y presupuesto transparente.',
    items: ['Propuesta técnica', 'Timeline detallado', 'Presupuesto claro'],
    icon: ClipboardIcon,
    variant: 'accent' as const,
  },
  {
    stepNumber: '03',
    title: 'Desarrollo',
    description: 'Código limpio y pruebas exhaustivas para máxima calidad.',
    items: ['Desarrollo ágil', 'Testing continuo', 'Feedback constante'],
    icon: CodeIcon,
    variant: 'success' as const,
  },
])

const secondRowSteps = computed(() => [
  {
    stepNumber: '04',
    title: 'Lanzamiento',
    description: 'Despliegue seguro y optimizado para el éxito.',
    items: ['Despliegue seguro', 'Optimización SEO', 'Configuración SSL'],
    icon: LightningIcon,
    variant: 'mixed' as const,
  },
  {
    stepNumber: '05',
    title: 'Soporte',
    description: 'Acompañamiento continuo para el crecimiento de tu proyecto.',
    items: ['Soporte 24/7', 'Mantenimiento', 'Mejoras continuas'],
    icon: CogIcon,
    variant: 'mixed' as const,
  },
])

defineExpose({
  processTitle,
  progressLine,
  firstRowRefs,
  secondRowRefs,
  currentProcessStep,
})
</script>
