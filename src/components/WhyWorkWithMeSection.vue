<template>
  <section class="vapor-section glass-section">
    <div class="vapor-section-content">
      <div class="vapor-section-header">
        <h2 class="vapor-section-title vapor-fade-in" ref="whyTitle">
          {{ title }}
        </h2>
        <p class="vapor-section-subtitle vapor-fade-in">
          {{ subtitle }}
        </p>
      </div>

      <div class="grid grid-cols-1 lg:grid-cols-2 gap-16 lg:gap-20 items-center">
        <!-- Left content -->
        <div class="space-y-8">
          <div class="flex items-start space-x-6 mb-8">
            <div
              class="w-16 h-16 bg-gradient-to-br from-cyan-100 to-sky-100 rounded-xl flex items-center justify-center flex-shrink-0"
            >
              <svg
                class="w-8 h-8 text-cyan-600"
                fill="none"
                stroke="currentColor"
                viewBox="0 0 24 24"
              >
                <path
                  stroke-linecap="round"
                  stroke-linejoin="round"
                  stroke-width="2"
                  d="M9 12l2 2 4-4m6 2a9 9 0 11-18 0 9 9 0 0118 0z"
                ></path>
              </svg>
            </div>
            <div class="space-y-4">
              <h3 class="heading-sm mb-6">Soluciones que entienden tu mercado</h3>
              <p class="text-body-md text-slate-700 mb-6 leading-relaxed">{{ description }}</p>
              <p class="text-body-md text-slate-700 leading-relaxed">{{ additionalDescription }}</p>
            </div>
          </div>
          <div class="grid grid-cols-1 sm:grid-cols-2 gap-4">
            <div
              class="flex items-center space-x-3 p-4 bg-gradient-to-r from-cyan-50 to-sky-50 rounded-xl hover:from-cyan-100 hover:to-sky-100 transition-all duration-300 group"
            >
              <div
                class="w-3 h-3 bg-cyan-500 rounded-full group-hover:scale-125 transition-transform duration-300"
              ></div>
              <span class="text-sm font-medium text-slate-700">Desarrollo personalizado</span>
            </div>
            <div
              class="flex items-center space-x-3 p-4 bg-gradient-to-r from-sky-50 to-cyan-50 rounded-xl hover:from-sky-100 hover:to-cyan-100 transition-all duration-300 group"
            >
              <div
                class="w-3 h-3 bg-sky-500 rounded-full group-hover:scale-125 transition-transform duration-300"
              ></div>
              <span class="text-sm font-medium text-slate-700">Comunicación clara</span>
            </div>
            <div
              class="flex items-center space-x-3 p-4 bg-gradient-to-r from-violet-50 to-violet-100/50 rounded-xl hover:from-violet-100 hover:to-violet-200/50 transition-all duration-300 group"
            >
              <div
                class="w-3 h-3 bg-violet-500 rounded-full group-hover:scale-125 transition-transform duration-300"
              ></div>
              <span class="text-sm font-medium text-slate-700">Resultados medibles</span>
            </div>
            <div
              class="flex items-center space-x-3 p-4 bg-gradient-to-r from-cyan-50 to-sky-50 rounded-xl hover:from-cyan-100 hover:to-sky-100 transition-all duration-300 group"
            >
              <div
                class="w-3 h-3 bg-cyan-500 rounded-full group-hover:scale-125 transition-transform duration-300"
              ></div>
              <span class="text-sm font-medium text-slate-700">Soporte continuo</span>
            </div>
          </div>
        </div>

        <!-- Right image with floating stats -->
        <div class="relative" ref="whyImage">
          <div class="relative">
            <img
              :src="image"
              :alt="imageAlt"
              class="rounded-2xl shadow-large object-cover w-full h-96"
            />
            <div
              class="absolute inset-0 bg-gradient-to-t from-blue-900/30 via-transparent to-purple-900/20 rounded-2xl"
            ></div>
            <div class="absolute bottom-6 left-6 glass-card-floating p-4">
              <div class="text-center">
                <div class="text-2xl font-bold text-cyan-600">20+</div>
                <div class="text-sm text-slate-600">Proyectos exitosos</div>
              </div>
            </div>
            <div class="absolute top-6 right-6 glass-card-floating p-4">
              <div class="text-center">
                <div class="text-2xl font-bold text-sky-600">7+</div>
                <div class="text-sm text-slate-600">Años de experiencia</div>
              </div>
            </div>
            <div
              class="absolute top-1/2 left-1/2 transform -translate-x-1/2 -translate-y-1/2 glass-card-floating w-24 h-24 flex items-center justify-center"
            >
              <div class="text-center">
                <div class="text-xl font-bold text-violet-600">100%</div>
                <div class="text-xs text-slate-600">Compromiso</div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
import { ref } from 'vue'

interface Props {
  title?: string
  subtitle?: string
  description?: string
  additionalDescription?: string
  image?: string
  imageAlt?: string
}

withDefaults(defineProps<Props>(), {
  title: 'Tu socio tecnológico, sin intermediarios',
  subtitle: 'Experiencia técnica + Visión de negocio',
  description:
    'Dirijo personalmente cada proyecto web, combinando mi expertise técnico con una comprensión profunda de tu negocio. Desde la estrategia hasta el código, todo pasa por mis manos.',
  additionalDescription:
    'No más soluciones estándar que no se adaptan a tu realidad. Construyo aplicaciones web personalizadas que entienden tu mercado, resuelven tus desafíos únicos y generan los resultados que tu negocio necesita.',
  image:
    'https://images.unsplash.com/photo-1551434678-e076c223a692?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1000&q=80',
  imageAlt: 'Desarrollo web profesional',
})

const whyTitle = ref<HTMLElement>()
const whyContent = ref<HTMLElement>()
const whyImage = ref<HTMLElement>()

defineExpose({
  whyTitle,
  whyContent,
  whyImage,
})
</script>
