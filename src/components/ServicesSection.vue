<template>
  <div class="max-w-5xl mx-auto">
    <h2 class="text-4xl md:text-5xl font-bold text-black text-center mb-8" ref="servicesTitle">
      {{ title }}
    </h2>

    <div class="text-center mb-16">
      <span
        class="inline-block bg-gray-100 text-gray-600 px-4 py-2 rounded-full text-sm font-medium"
      >
        Servicios
      </span>
    </div>

    <div class="grid md:grid-cols-2 gap-12 mb-16">
      <div
        v-for="(service, index) in services"
        :key="index"
        class="group relative"
        ref="serviceRefs"
      >
        <div
          class="bg-white rounded-2xl p-8 md:p-10 shadow-sm border border-gray-100 hover:shadow-lg transition-all duration-300 group-hover:border-gray-200"
        >
          <div class="flex items-start space-x-6">
            <div class="flex-shrink-0">
              <div
                class="w-16 h-16 bg-gray-50 rounded-xl flex items-center justify-center group-hover:bg-gray-100 transition-colors duration-300"
              >
                <component :is="service.icon" class="w-8 h-8 text-black" />
              </div>
            </div>
            <div class="flex-1">
              <h3
                class="text-2xl font-bold text-black mb-4 group-hover:text-gray-800 transition-colors duration-300"
              >
                {{ service.title }}
              </h3>
              <p class="text-gray-600 leading-relaxed text-lg">
                {{ service.description }}
              </p>
              <div class="mt-6">
                <ul class="space-y-3">
                  <li
                    v-for="(feature, featureIndex) in service.features"
                    :key="featureIndex"
                    class="flex items-center text-gray-600"
                  >
                    <div class="w-2 h-2 bg-black rounded-full mr-3 flex-shrink-0"></div>
                    <span class="text-base">{{ feature }}</span>
                  </li>
                </ul>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>

    <!-- Call to Action -->
    <div class="text-center bg-white rounded-2xl p-8 md:p-12 shadow-sm border border-gray-100">
      <h3 class="text-2xl md:text-3xl font-bold text-black mb-4">
        ¿Listo para empezar tu proyecto?
      </h3>
      <p class="text-lg text-gray-600 mb-8 max-w-2xl mx-auto">
        Cuéntame sobre tu negocio y cómo puedo ayudarte a alcanzar tus objetivos. Trabajemos juntos
        para crear algo extraordinario.
      </p>
      <div class="flex flex-col sm:flex-row gap-4 justify-center">
        <a href="#contacto" class="btn-primary text-lg group" @click.prevent="scrollToContact">
          Hablemos de tu proyecto
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
              d="M17 8l4 4m0 0l-4 4m4-4H3"
            ></path>
          </svg>
        </a>
        <a href="#proceso" class="btn-secondary text-lg group" @click.prevent="scrollToProcess">
          Conoce mi proceso
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
              d="M19 9l-7 7-7-7"
            ></path>
          </svg>
        </a>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
import { ref, computed } from 'vue'
import { Globe, Database } from 'lucide-vue-next'
import { gsap } from 'gsap'
import { ScrollToPlugin } from 'gsap/ScrollToPlugin'

// Register the ScrollToPlugin
gsap.registerPlugin(ScrollToPlugin)

interface Props {
  title?: string
}

withDefaults(defineProps<Props>(), {
  title: '¿De qué forma puedo ayudarte?',
})

const servicesTitle = ref<HTMLElement>()
const serviceRefs = ref<HTMLElement[]>([])
const servicesNote = ref<HTMLElement>()

// Services data - only 2 services with more elegant design
const services = computed(() => [
  {
    title: 'Páginas web efectivas',
    description:
      'Sitios web profesionales y administrables que convierten visitantes en clientes. Diseñados para campañas, productos o servicios específicos.',
    icon: Globe,
    features: [
      'Sitios web con WordPress administrable',
      'Optimizados para conversiones',
      'Diseño responsive y moderno',
      'Integración con herramientas de marketing',
    ],
  },
  {
    title: 'Sistemas internos',
    description:
      'Automatización de procesos internos para mejorar la eficiencia de tu negocio. Integraciones inteligentes que ahorran tiempo y recursos.',
    icon: Database,
    features: [
      'Automatización de tareas repetitivas',
      'Integración con pagos y CRMs',
      'Sistemas contables personalizados',
      'Dashboards de control y reportes',
    ],
  },
])

// Function to scroll to contact section
const scrollToContact = () => {
  const contactSection = document.querySelector('#contacto') as HTMLElement
  if (contactSection) {
    gsap.to(window, {
      duration: 1,
      scrollTo: {
        y: contactSection,
        offsetY: 100,
      },
      ease: 'power2.inOut',
    })
  }
}

// Function to scroll to process section
const scrollToProcess = () => {
  const processSection = document.querySelector('#proceso') as HTMLElement
  if (processSection) {
    gsap.to(window, {
      duration: 1,
      scrollTo: {
        y: processSection,
        offsetY: 100,
      },
      ease: 'power2.inOut',
    })
  }
}

defineExpose({
  servicesTitle,
  serviceRefs,
  servicesNote,
})
</script>
