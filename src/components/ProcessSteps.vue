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

      <!-- Enhanced CTA section with glassmorphism design -->
      <div class="relative mt-16 lg:mt-20">
        <!-- Background with glassmorphism effect -->
        <div class="absolute inset-0 glass-bg-secondary rounded-3xl"></div>
        <div class="absolute inset-0 opacity-5">
          <div class="absolute inset-0 isometric-grid"></div>
        </div>

        <div class="relative z-10 p-12">
          <h3 class="vapor-cta-title mb-4 text-center">
            ¿Te gustaría conocer más sobre mi proceso?
          </h3>
          <p class="vapor-cta-description mb-8 text-center">
            Platicamos sobre tu proyecto y te explico paso a paso cómo trabajo. Sin compromisos,
            solo información clara para que sepas exactamente qué esperar.
          </p>
          <!-- CTA buttons -->
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
import { ref, computed } from 'vue'
import ProcessStep from './ProcessStep.vue'
import ChatIcon from './icons/ChatIcon.vue'
import ClipboardIcon from './icons/ClipboardIcon.vue'
import CodeIcon from './icons/CodeIcon.vue'
import LightningIcon from './icons/LightningIcon.vue'

interface Props {
  title?: string
  subtitle?: string
}

withDefaults(defineProps<Props>(), {
  title: '¿Cómo trabajo?',
  subtitle: 'Un proceso simple y efectivo para llevar tu proyecto al siguiente nivel',
})

const processTitle = ref<HTMLElement>()
const stepRefs = ref<HTMLElement[]>([])

// All process steps in a single array for simpler grid layout
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
    icon: ChatIcon,
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
    icon: ClipboardIcon,
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
    icon: CodeIcon,
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
    icon: LightningIcon,
    variant: 'mixed' as const,
  },
])

defineExpose({
  processTitle,
  stepRefs,
})
</script>
