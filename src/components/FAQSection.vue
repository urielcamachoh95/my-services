<template>
  <section class="vapor-section glass-section">
    <div class="vapor-section-content">
      <div class="vapor-section-header">
        <h2 class="vapor-section-title vapor-fade-in" ref="faqTitle">
          {{ title }}
        </h2>
        <p class="vapor-section-subtitle vapor-fade-in">
          {{ subtitle }}
        </p>
      </div>

      <div class="max-w-4xl mx-auto">
        <div class="space-y-4">
          <div
            v-for="(faq, index) in faqs"
            :key="index"
            class="bg-white/80 backdrop-blur-sm rounded-2xl border border-white/30 shadow-sm hover:shadow-md transition-all duration-300"
            :class="{ 'ring-2 ring-cyan-100': faq.isOpen }"
          >
            <button
              @click="toggleFAQ(index)"
              class="w-full px-6 py-4 text-left flex items-center justify-between group hover:bg-cyan-50/50 transition-colors duration-300 rounded-2xl"
            >
              <h3
                class="text-lg font-semibold text-slate-800 group-hover:text-cyan-700 transition-colors duration-300"
              >
                {{ faq.question }}
              </h3>
              <svg
                class="w-5 h-5 text-slate-400 group-hover:text-cyan-600 transition-all duration-300 flex-shrink-0"
                :class="{ 'rotate-180': faq.isOpen }"
                fill="none"
                stroke="currentColor"
                viewBox="0 0 24 24"
              >
                <path
                  stroke-linecap="round"
                  stroke-linejoin="round"
                  stroke-width="2"
                  d="M19 9l-7 7-7-7"
                />
              </svg>
            </button>

            <div v-show="faq.isOpen" class="px-6 pb-4">
              <div class="text-slate-600 leading-relaxed space-y-3">
                <p>{{ faq.answer }}</p>
                <div v-if="faq.details" class="bg-cyan-50/50 rounded-xl p-3 border border-cyan-100">
                  <h4 class="font-medium text-cyan-800 mb-2">{{ faq.details.title }}</h4>
                  <ul class="space-y-1">
                    <li
                      v-for="(detail, detailIndex) in faq.details.items"
                      :key="detailIndex"
                      class="flex items-start gap-3 text-sm text-cyan-700"
                    >
                      <div class="w-2 h-2 bg-cyan-500 rounded-full mt-2 flex-shrink-0"></div>
                      <span>{{ detail }}</span>
                    </li>
                  </ul>
                </div>
              </div>
            </div>
          </div>
        </div>

        <!-- CTA Section -->
        <div class="mt-8 text-center">
          <p class="text-slate-600 mb-4">¿Tienes alguna otra pregunta? Estoy aquí para ayudarte.</p>
          <div class="flex flex-col sm:flex-row gap-4 justify-center">
            <a
              href="https://wa.me/+5212212287141?text=Hola%20Uriel,%20tengo%20una%20pregunta%20sobre%20mi%20proyecto%20web"
              target="_blank"
              rel="noopener noreferrer"
              class="vapor-btn-primary group"
            >
              <svg class="w-5 h-5 mr-2" fill="currentColor" viewBox="0 0 24 24">
                <path
                  d="M20.52 3.449C18.24 1.245 15.24 0 12.045 0 5.463 0 .104 5.334.101 11.893c0 2.096.547 4.142 1.588 5.945L.057 24l6.305-1.654a11.882 11.882 0 005.683 1.448h.005c6.554 0 11.89-5.335 11.893-11.893A11.821 11.821 0 0020.52 3.449zM12.05 21.49c-1.554 0-3.146-.428-4.5-1.08l-.361-.214-3.75.982.998-3.648-.235-.374a9.86 9.86 0 01-1.51-5.26c.001-5.45 4.436-9.884 9.888-9.884 2.64 0 5.122 1.03 6.988 2.898a9.825 9.825 0 012.893 6.994c-.003 5.45-4.437 9.884-9.885 9.884z"
                />
                <path
                  d="M17.472 14.382c-.297-.149-1.758-.867-2.03-.967-.273-.099-.471-.148-.67.15-.197.297-.767.966-.94 1.164-.173.199-.347.223-.644.075-.297-.15-1.255-.463-2.39-1.475-.883-.788-1.48-1.761-1.653-2.059-.173-.297-.018-.458.13-.606.134-.133.298-.347.446-.52.149-.174.198-.298.298-.497.099-.198.05-.371-.025-.52-.075-.149-.669-1.612-.916-2.207-.242-.579-.487-.5-.669-.51-.173-.008-.371-.01-.57-.01-.198 0-.52.074-.792.372-.272.297-1.04 1.016-1.04 2.479 0 1.462 1.065 2.875 1.213 3.074.149.198 2.096 3.2 5.077 4.487.709.306 1.262.489 1.694.625.712.227 1.36.195 1.871.118.571-.085 1.758-.719 2.006-1.413.248-.694.248-1.289.173-1.413-.074-.124-.272-.198-.57-.347"
                />
              </svg>
              Preguntar por WhatsApp
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
            <a href="#contacto" class="vapor-btn-secondary group">
              Ver más opciones de contacto
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
                  d="M21 3l-6 6m0 0V4m0 5h5M5 3a2 2 0 00-2 2v1c0 8.284 6.716 15 15 15h1a2 2 0 002-2v-3.28a1 1 0 00-.684-.948l-4.493-1.498a1 1 0 00-1.21.502l-1.13 2.257a11.042 11.042 0 01-5.516-5.517l2.257-1.128a1 1 0 00.502-1.21L9.228 3.683A1 1 0 008.279 3H5z"
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
import { ref, onMounted } from 'vue'

interface FAQDetail {
  title: string
  items: string[]
}

interface FAQ {
  question: string
  answer: string
  details?: FAQDetail
  isOpen: boolean
}

interface Props {
  title?: string
  subtitle?: string
}

withDefaults(defineProps<Props>(), {
  title: 'Preguntas Frecuentes',
  subtitle: 'Resuelvo las dudas más comunes sobre mis servicios de desarrollo web',
})

const faqTitle = ref<HTMLElement>()

// FAQ data with relevant content for web development services
const faqs = ref<FAQ[]>([
  {
    question: '¿Cuánto tiempo toma desarrollar un sitio web?',
    answer:
      'El tiempo de desarrollo varía según la complejidad del proyecto. Un sitio web básico puede tomar 2-3 semanas, mientras que un e-commerce completo puede requerir 4-6 semanas.',
    details: {
      title: 'Timeline típico por tipo de proyecto:',
      items: [
        'Sitio web corporativo: 2-3 semanas',
        'E-commerce básico: 3-4 semanas',
        'Sistema de reservas: 4-5 semanas',
        'Aplicación web personalizada: 6-8 semanas',
      ],
    },
    isOpen: false,
  },
  {
    question: '¿Cuál es el costo de un sitio web?',
    answer:
      'Los precios varían según las funcionalidades y complejidad. Trabajo con presupuestos transparentes y te entrego una propuesta detallada sin sorpresas.',
    details: {
      title: 'Rangos de precios aproximados:',
      items: [
        'Sitio web básico: $15,000 - $25,000 MXN',
        'E-commerce completo: $35,000 - $60,000 MXN',
        'Sistema personalizado: $50,000 - $100,000 MXN',
        'Mantenimiento mensual: $3,000 - $8,000 MXN',
      ],
    },
    isOpen: false,
  },
  {
    question: '¿Qué incluye el servicio completo?',
    answer:
      'Mi servicio incluye diseño, desarrollo, pruebas, despliegue, configuración del servidor, y capacitación para que puedas administrar tu sitio.',
    details: {
      title: 'Todo lo que recibes:',
      items: [
        'Diseño responsivo y moderno',
        'Desarrollo con código limpio y optimizado',
        'Pruebas en múltiples dispositivos',
        'Despliegue seguro y optimizado',
        'Capacitación y documentación',
        '3 meses de soporte post-entrega',
      ],
    },
    isOpen: false,
  },
  {
    question: '¿Puedes trabajar con mi presupuesto actual?',
    answer:
      'Sí, siempre encuentro la mejor solución para tu presupuesto. Te propongo alternativas y priorizamos las funcionalidades más importantes para tu negocio.',
    details: {
      title: 'Opciones de financiamiento:',
      items: [
        'Pago en 2-3 partes durante el desarrollo',
        'Plan de funcionalidades por fases',
        'Solución básica con opción de crecimiento',
        'Mantenimiento incluido en el precio',
      ],
    },
    isOpen: false,
  },
  {
    question: '¿Qué tecnologías utilizas?',
    answer:
      'Trabajo con las tecnologías más modernas y confiables del mercado, incluyendo WordPress, Shopify, y desarrollo personalizado con las mejores prácticas.',
    details: {
      title: 'Stack tecnológico:',
      items: [
        'Frontend: HTML5, CSS3, JavaScript, Vue.js',
        'CMS: WordPress, Shopify',
        'Backend: Node.js, PHP, Python',
        'Bases de datos: MySQL, PostgreSQL',
        'Hosting: Servidores optimizados y seguros',
      ],
    },
    isOpen: false,
  },
  {
    question: '¿Ofreces mantenimiento después del lanzamiento?',
    answer:
      'Sí, ofrezco planes de mantenimiento que incluyen actualizaciones de seguridad, respaldos, monitoreo, y soporte técnico para asegurar que tu sitio funcione perfectamente.',
    details: {
      title: 'Planes de mantenimiento:',
      items: [
        'Actualizaciones de seguridad automáticas',
        'Respaldo diario de tu sitio',
        'Monitoreo 24/7 del rendimiento',
        'Soporte técnico prioritario',
        'Reportes mensuales de funcionamiento',
      ],
    },
    isOpen: false,
  },
  {
    question: '¿Puedes mejorar mi sitio web existente?',
    answer:
      '¡Por supuesto! Puedo optimizar, rediseñar, o agregar nuevas funcionalidades a tu sitio actual. Primero analizo lo que tienes y te propongo las mejoras más efectivas.',
    details: {
      title: 'Servicios de mejora:',
      items: [
        'Auditoría técnica y de rendimiento',
        'Rediseño y modernización',
        'Optimización para móviles',
        'Mejoras de velocidad y SEO',
        'Integración de nuevas funcionalidades',
      ],
    },
    isOpen: false,
  },
  {
    question: '¿Cómo funciona el proceso de trabajo?',
    answer:
      'Mi proceso es simple y transparente: conversamos sobre tus necesidades, te presento una propuesta clara, desarrollamos tu proyecto paso a paso, y te entrego todo listo para usar.',
    details: {
      title: 'Proceso de 4 pasos:',
      items: [
        'Conversamos: Entrevista y análisis de necesidades',
        'Planificamos: Propuesta técnica y presupuesto',
        'Construimos: Desarrollo iterativo con feedback',
        'Entregamos: Despliegue y capacitación',
      ],
    },
    isOpen: false,
  },
])

// Toggle FAQ open/close state
const toggleFAQ = (index: number) => {
  faqs.value[index].isOpen = !faqs.value[index].isOpen

  // Close other FAQs (optional - for accordion behavior)
  faqs.value.forEach((faq, i) => {
    if (i !== index) {
      faq.isOpen = false
    }
  })
}

// Auto-open first FAQ for better UX
onMounted(() => {
  if (faqs.value.length > 0) {
    faqs.value[0].isOpen = true
  }
})

defineExpose({
  faqTitle,
})
</script>

<style scoped>
/* Smooth accordion animations */
.faq-enter-active,
.faq-leave-active {
  transition: all 0.3s ease;
}

.faq-enter-from,
.faq-leave-to {
  opacity: 0;
  transform: translateY(-10px);
}
</style>
