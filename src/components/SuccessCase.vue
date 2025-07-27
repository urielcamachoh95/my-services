<template>
  <div
    class="bg-white rounded-3xl p-8 md:p-12 shadow-sm border border-gray-100 transition-all duration-700 ease-out"
    :class="[
      isActive
        ? 'translate-x-0 opacity-100 scale-100 blur-0 relative z-10'
        : 'absolute inset-0 translate-x-full opacity-40 scale-90 -translate-y-8 blur-sm z-0',
    ]"
    ref="successCase"
  >
    <div class="grid md:grid-cols-2 gap-12 items-center">
      <div class="space-y-6">
        <div
          class="inline-flex items-center gap-3 bg-gray-100 text-black px-4 py-2 rounded-full text-sm font-medium"
        >
          <svg class="w-5 h-5" fill="none" stroke="currentColor" viewBox="0 0 24 24">
            <path
              stroke-linecap="round"
              stroke-linejoin="round"
              stroke-width="2"
              d="M9 12l2 2 4-4m6 2a9 9 0 11-18 0 9 9 0 0118 0z"
            ></path>
          </svg>
          {{ badgeText }}
        </div>

        <h3 class="text-3xl md:text-4xl font-bold text-black leading-tight">
          {{ title }}
        </h3>

        <p class="text-lg text-gray-600 leading-relaxed">
          {{ description }}
        </p>

        <div class="space-y-4">
          <div v-for="(feature, index) in features" :key="index" class="flex items-start gap-4">
            <div
              class="w-8 h-8 rounded-lg flex items-center justify-center flex-shrink-0 mt-1"
              :class="feature.iconBgClass"
            >
              <component :is="feature.icon" :class="feature.iconClass" />
            </div>
            <p class="text-gray-600 leading-relaxed">{{ feature.text }}</p>
          </div>
        </div>

        <div class="flex flex-wrap gap-3">
          <span
            v-for="(tag, index) in tags"
            :key="index"
            class="px-3 py-1 rounded-full text-sm font-medium"
            :class="tag.class"
          >
            {{ tag.text }}
          </span>
        </div>
      </div>

      <div class="relative">
        <img
          :src="image"
          :alt="imageAlt"
          class="rounded-2xl shadow-sm border border-gray-100 object-cover w-full h-96"
        />
        <div
          class="absolute inset-0 bg-gradient-to-t from-black/10 to-transparent rounded-2xl"
        ></div>

        <!-- Stats overlay -->
        <div
          class="absolute bottom-6 left-6 right-6 bg-white/90 backdrop-blur-sm rounded-xl p-4 border border-gray-100"
        >
          <div class="grid grid-cols-2 gap-4">
            <div v-for="(stat, index) in stats" :key="index" class="text-center">
              <div class="text-2xl font-bold mb-1" :class="stat.valueClass">
                {{ stat.value }}
              </div>
              <div class="text-sm text-gray-600">{{ stat.label }}</div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
import { ref } from 'vue'
import type { Component } from 'vue'

interface Feature {
  text: string
  icon: Component
  iconBgClass: string
  iconClass: string
}

interface Tag {
  text: string
  class: string
}

interface Stat {
  value: string
  label: string
  valueClass: string
}

interface Props {
  title: string
  description: string
  image: string
  imageAlt: string
  badgeText?: string
  features: Feature[]
  tags: Tag[]
  stats: Stat[]
  isActive?: boolean
}

withDefaults(defineProps<Props>(), {
  badgeText: 'Caso de éxito',
  isActive: false,
})

const successCase = ref<HTMLElement>()

defineExpose({
  successCase,
})
</script>
