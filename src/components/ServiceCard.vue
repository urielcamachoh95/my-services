<template>
  <div
    class="group bg-white rounded-2xl p-8 shadow-lg border border-neutral-300 hover:shadow-2xl transition-all duration-500 hover:-translate-y-2"
    ref="serviceCard"
  >
    <div
      class="w-16 h-16 bg-primary-500 rounded-2xl flex items-center justify-center mb-6 group-hover:scale-110 transition-transform duration-300"
    >
      <component :is="icon" class="w-8 h-8 text-white" />
    </div>
    <h3 class="text-2xl font-semibold text-text mb-4">{{ title }}</h3>
    <p class="text-text/70 leading-relaxed mb-6">{{ description }}</p>
    <img :src="image" :alt="imageAlt" class="w-full h-48 object-cover rounded-xl" />
  </div>
</template>

<script setup lang="ts">
import { ref } from 'vue'
import type { Component } from 'vue'

interface Props {
  title: string
  description: string
  image: string
  imageAlt: string
  icon: Component
}

defineProps<Props>()

const serviceCard = ref<HTMLElement>()

defineExpose({
  serviceCard,
})
</script>
