<template>
  <section class="vapor-section glass-section">
    <div class="vapor-section-content">
      <div class="vapor-section-header">
        <h2 class="vapor-section-title vapor-fade-in" ref="servicesTitle">
          {{ title }}
        </h2>
        <p class="vapor-section-subtitle vapor-fade-in vapor-component-spacing-compact">
          {{ subtitle }}
        </p>
      </div>

      <!-- Service Summary Section -->
      <div class="vapor-section-margin-tight text-center">
        <div class="max-w-4xl mx-auto">
          <h3 class="text-xl font-semibold text-slate-800 vapor-component-spacing">
            ¿Qué tipo de proyecto necesitas?
          </h3>
          <div class="vapor-grid-normal grid grid-cols-1 md:grid-cols-3">
            <div
              class="glass-card text-center vapor-card-spacing-compact hover:shadow-lg hover:-translate-y-1 transition-all duration-300"
            >
              <div
                class="w-14 h-14 bg-cyan-100 rounded-xl flex items-center justify-center mx-auto vapor-component-spacing-compact"
              >
                <svg
                  class="w-7 h-7 text-cyan-600"
                  fill="none"
                  stroke="currentColor"
                  viewBox="0 0 24 24"
                >
                  <path
                    stroke-linecap="round"
                    stroke-linejoin="round"
                    stroke-width="2"
                    d="M13 10V3L4 14h7v7l9-11h-7z"
                  />
                </svg>
              </div>
              <h4 class="text-lg font-semibold text-slate-800 vapor-component-spacing-tight">
                Landing Pages
              </h4>
              <p class="text-slate-600 text-sm">
                Páginas de aterrizaje que convierten visitantes en clientes
              </p>
            </div>

            <div
              class="glass-card text-center vapor-card-spacing-compact hover:shadow-lg hover:-translate-y-1 transition-all duration-300"
            >
              <div
                class="w-14 h-14 bg-sky-100 rounded-xl flex items-center justify-center mx-auto vapor-component-spacing-compact"
              >
                <svg
                  class="w-7 h-7 text-sky-600"
                  fill="none"
                  stroke="currentColor"
                  viewBox="0 0 24 24"
                >
                  <path
                    stroke-linecap="round"
                    stroke-linejoin="round"
                    stroke-width="2"
                    d="M16 11V7a4 4 0 00-8 0v4M5 9h14l1 12H4L5 9z"
                  />
                </svg>
              </div>
              <h4 class="text-lg font-semibold text-slate-800 vapor-component-spacing-tight">
                E-commerce
              </h4>
              <p class="text-slate-600 text-sm">Tiendas online completas que venden 24/7</p>
            </div>

            <div
              class="glass-card text-center vapor-card-spacing-compact hover:shadow-lg hover:-translate-y-1 transition-all duration-300"
            >
              <div
                class="w-14 h-14 bg-violet-100 rounded-xl flex items-center justify-center mx-auto vapor-component-spacing-compact"
              >
                <svg
                  class="w-7 h-7 text-violet-600"
                  fill="none"
                  stroke="currentColor"
                  viewBox="0 0 24 24"
                >
                  <path
                    stroke-linecap="round"
                    stroke-linejoin="round"
                    stroke-width="2"
                    d="M9.75 17L9 20l-1 1h8l-1-1-.75-3M3 13h18M5 17h14a2 2 0 002-2V5a2 2 0 00-2-2H5a2 2 0 00-2 2v10a2 2 0 002 2z"
                  />
                </svg>
              </div>
              <h4 class="text-lg font-semibold text-slate-800 vapor-component-spacing-tight">
                Aplicaciones Complejas
              </h4>
              <p class="text-slate-600 text-sm">
                Sistemas personalizados que automatizan tu negocio
              </p>
            </div>
          </div>
        </div>
      </div>
      <!-- Enhanced CTA section with glassmorphism design -->
      <div class="relative vapor-section-margin-compact">
        <!-- Background with glassmorphism effect -->
        <div class="glass-card rounded-3xl p-8">
          <div class="text-center">
            <h3 class="vapor-cta-title vapor-component-spacing-tight">
              ¿Te gustaría platicar sobre tu proyecto?
            </h3>
            <p class="vapor-cta-description vapor-component-spacing">
              Cuéntame sobre tu negocio y veamos juntos cómo puedo ayudarte. La primera conversación
              es sin compromiso, solo para entender mejor lo que necesitas.
            </p>
            <div class="vapor-cta-buttons">
              <a
                href="https://wa.me/+5212212287141?text=Hola%20Uriel,%20me%20interesa%20trabajar%20contigo%20en%20mi%20proyecto"
                target="_blank"
                rel="noopener noreferrer"
                class="vapor-btn-primary text-lg group"
              >
                <svg class="w-5 h-5 mr-2" fill="currentColor" viewBox="0 0 24 24">
                  <path
                    d="M17.472 14.382c-.297-.149-1.758-.867-2.03-.967-.273-.099-.471-.148-.67.15-.197.297-.767.966-.94 1.164-.173.199-.347.223-.644.075-.297-.15-1.255-.463-2.39-1.475-.883-.788-1.48-1.761-1.653-2.059-.173-.297-.018-.458.13-.606.134-.133.298-.347.446-.52.149-.174.198-.298.298-.497.099-.198.05-.371-.025-.52-.075-.149-.669-1.612-.916-2.207-.242-.579-.487-.5-.669-.51-.173-.008-.371-.01-.57-.01-.198 0-.52.074-.792.372-.272.297-1.04 1.016-1.04 2.479 0 1.462 1.065 2.875 1.213 3.074.149.198 2.096 3.2 5.077 4.487.709.306 1.262.489 1.694.625.712.227 1.36.195 1.871.118.571-.085 1.758-.719 2.006-1.413.248-.694.248-1.289.173-1.413-.074-.124-.272-.198-.57-.347m-5.421 7.403h-.004a9.87 9.87 0 01-5.031-1.378l-.361-.214-3.741.982.998-3.648-.235-.374a9.86 9.86 0 01-1.51-5.26c.001-5.45 4.436-9.884 9.888-9.884 2.64 0 5.122 1.03 6.988 2.898a9.825 9.825 0 012.893 6.994c-.003 5.45-4.437 9.884-9.885 9.884m8.413-18.297A11.815 11.815 0 0012.05 0C5.495 0 .16 5.335.157 11.892c0 2.096.547 4.142 1.588 5.945L.057 24l6.305-1.654a11.882 0 005.683 1.448h.005c6.554 0 11.89-5.335 11.893-11.893A11.821 11.821 0 0020.885 3.488"
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
              <a
                href="#proceso"
                class="vapor-btn-secondary text-lg group"
                @click.prevent="scrollToProcess"
              >
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
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
import { ref, computed } from 'vue'
import { Globe, Database } from 'lucide-vue-next'

interface Props {
  title?: string
  subtitle?: string
}

withDefaults(defineProps<Props>(), {
  title: '¿De qué forma puedo ayudarte?',
  subtitle: 'Soluciones web completas diseñadas para hacer crecer tu negocio de manera efectiva',
})

const servicesTitle = ref<HTMLElement>()
const serviceRefs = ref<HTMLElement[]>([])
const servicesNote = ref<HTMLElement>()

// Services data - only 2 services with more elegant design
const services = computed(() => [
  {
    title: 'Páginas web que convierten',
    description:
      'Sitios web profesionales y administrables diseñados para convertir visitantes en clientes. Cada página está optimizada para tu negocio específico.',
    icon: Globe,
    variant: 'primary' as const,
    features: [
      'Sitios web con WordPress fácil de administrar',
      'Optimizados para conversiones y ventas',
      'Diseño responsive que funciona en todos los dispositivos',
      'Integración con herramientas de marketing que ya usas',
    ],
  },
  {
    title: 'Sistemas que ahorran tiempo',
    description:
      'Automatización de procesos internos para que tu equipo se enfoque en lo importante. Integraciones inteligentes que ahorran tiempo y recursos.',
    icon: Database,
    variant: 'secondary' as const,
    features: [
      'Automatización de tareas repetitivas y aburridas',
      'Integración con sistemas de pagos y CRMs',
      'Sistemas contables personalizados para tu flujo',
      'Dashboards claros para tomar mejores decisiones',
    ],
  },
])

// Function to scroll to process section
const scrollToProcess = () => {
  const processSection = document.querySelector('#proceso') as HTMLElement
  if (processSection) {
    processSection.scrollIntoView({ behavior: 'smooth', block: 'start' })
  }
}

defineExpose({
  servicesTitle,
  serviceRefs,
  servicesNote,
})
</script>
