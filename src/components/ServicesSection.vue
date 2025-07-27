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
        <a
          href="https://wa.me/+5212212287141?text=Hola%20Uriel,%20me%20interesa%20trabajar%20contigo%20en%20mi%20proyecto"
          target="_blank"
          rel="noopener noreferrer"
          class="btn-primary text-lg group"
        >
          <svg class="w-5 h-5 mr-2" fill="currentColor" viewBox="0 0 24 24">
            <path
              d="M17.472 14.382c-.297-.149-1.758-.867-2.03-.967-.273-.099-.471-.148-.67.15-.197.297-.767.966-.94 1.164-.173.199-.347.223-.644.075-.297-.15-1.255-.463-2.39-1.475-.883-.788-1.48-1.761-1.653-2.059-.173-.297-.018-.458.13-.606.134-.133.298-.347.446-.52.149-.174.198-.298.298-.497.099-.198.05-.371-.025-.52-.075-.149-.669-1.612-.916-2.207-.242-.579-.487-.5-.669-.51-.173-.008-.371-.01-.57-.01-.198 0-.52.074-.792.372-.272.297-1.04 1.016-1.04 2.479 0 1.462 1.065 2.875 1.213 3.074.149.198 2.096 3.2 5.077 4.487.709.306 1.262.489 1.694.625.712.227 1.36.195 1.871.118.571-.085 1.758-.719 2.006-1.413.248-.694.248-1.289.173-1.413-.074-.124-.272-.198-.57-.347m-5.421 7.403h-.004a9.87 9.87 0 01-5.031-1.378l-.361-.214-3.741.982.998-3.648-.235-.374a9.86 9.86 0 01-1.51-5.26c.001-5.45 4.436-9.884 9.888-9.884 2.64 0 5.122 1.03 6.988 2.898a9.825 9.825 0 012.893 6.994c-.003 5.45-4.437 9.884-9.885 9.884m8.413-18.297A11.815 11.815 0 0012.05 0C5.495 0 .16 5.335.157 11.892c0 2.096.547 4.142 1.588 5.945L.057 24l6.305-1.654a11.882 11.882 0 005.683 1.448h.005c6.554 0 11.89-5.335 11.893-11.893A11.821 11.821 0 0020.885 3.488"
            />
          </svg>
          Hablemos por WhatsApp
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
