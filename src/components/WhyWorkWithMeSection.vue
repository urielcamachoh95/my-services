<template>
  <div class="max-w-5xl mx-auto">
    <h2 class="text-4xl md:text-5xl font-bold text-black text-center mb-16" ref="whyTitle">
      {{ title }}
    </h2>

    <div class="grid md:grid-cols-2 gap-12 items-center">
      <div class="space-y-8" ref="whyContent">
        <div class="bg-white rounded-2xl p-8 md:p-12 shadow-sm border border-gray-100">
          <h3 class="text-2xl md:text-3xl font-bold text-black mb-6">
            {{ subtitle }}
          </h3>
          <p class="text-lg text-gray-600 mb-6 leading-relaxed">
            {{ description }}
          </p>
          <p class="text-lg text-gray-600 leading-relaxed">
            {{ additionalDescription }}
          </p>
        </div>
      </div>

      <div class="relative" ref="whyImage">
        <img
          :src="image"
          :alt="imageAlt"
          class="rounded-2xl shadow-sm border border-gray-100 object-cover w-full h-96"
        />
        <div
          class="absolute inset-0 bg-gradient-to-t from-black/10 to-transparent rounded-2xl"
        ></div>
      </div>
    </div>
  </div>
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
  title: '¿Por qué trabajar conmigo?',
  subtitle: 'Un aliado técnico, no una agencia más',
  description:
    'Soy desarrollador web full-stack enfocado en lograr resultados concretos. Lidero personalmente cada proyecto, desde la idea inicial hasta la entrega final.',
  additionalDescription:
    'No ofrezco paquetes genéricos. Cada solución parte de escuchar con atención, entender los retos de tu negocio y construir con claridad lo que realmente puede marcar una diferencia.',
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
