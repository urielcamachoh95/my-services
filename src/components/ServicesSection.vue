<template>
  <div class="max-w-5xl mx-auto" style="opacity: 1 !important; visibility: visible !important">
    <h2 class="text-4xl md:text-5xl font-bold text-black text-center mb-8" ref="servicesTitle">
      {{ title }}
    </h2>

    <div class="text-center mb-12">
      <span
        class="inline-block bg-gray-100 text-gray-600 px-3 py-1 rounded-full text-sm font-medium"
      >
        Servicios
      </span>
    </div>

    <div class="grid md:grid-cols-2 lg:grid-cols-4 gap-8 mb-12">
      <div v-for="(service, index) in services" :key="index" class="text-center" ref="serviceRefs">
        <div class="w-16 h-16 mx-auto mb-4 flex items-center justify-center">
          <component :is="service.icon" class="w-full h-full text-black" />
        </div>
        <h3 class="text-xl font-semibold text-black mb-3">{{ service.title }}</h3>
        <p class="text-gray-600 leading-relaxed">{{ service.description }}</p>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
import { ref, computed, onMounted } from 'vue'
import GlobeIcon from './icons/GlobeIcon.vue'
import CheckIcon from './icons/CheckIcon.vue'
import CodeIcon from './icons/CodeIcon.vue'
import CogIcon from './icons/CogIcon.vue'

interface Props {
  title?: string
}

withDefaults(defineProps<Props>(), {
  title: '¿De qué forma puedo ayudarte?',
})

const servicesTitle = ref<HTMLElement>()
const serviceRefs = ref<HTMLElement[]>([])
const servicesNote = ref<HTMLElement>()

// Services data - similar to the image reference
const services = computed(() => [
  {
    title: 'Páginas web efectivas',
    description:
      'Para campañas, productos o servicios. Sitios web administrables con WordPress, adaptadas a las necesidades de tu negocio.',
    icon: GlobeIcon,
  },
  {
    title: 'Sistemas internos',
    description:
      'Para automatizar tareas y mejorar procesos internos. Integraciones con pagos, CRMs, o sistemas contables.',
    icon: CheckIcon,
  },
  {
    title: 'Diseño y creatividad',
    description: 'Creando diseños visualmente impactantes que conectan con tu audiencia.',
    icon: CodeIcon,
  },
  {
    title: 'Desarrollo',
    description: 'Dando vida a tu visión con las últimas tecnologías y tendencias de diseño.',
    icon: CogIcon,
  },
])

onMounted(() => {
  console.log('ServicesSection mounted')
  console.log('servicesTitle:', servicesTitle.value)
  console.log('serviceRefs:', serviceRefs.value)
})

defineExpose({
  servicesTitle,
  serviceRefs,
  servicesNote,
})
</script>
