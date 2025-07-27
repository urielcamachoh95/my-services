<template>
  <div class="relative group" ref="processStep">
    <!-- Background effect -->
    <div
      class="absolute inset-0 bg-gray-50 rounded-3xl opacity-0 group-hover:opacity-100 transition-opacity duration-500"
    ></div>

    <div
      class="relative bg-white rounded-3xl p-6 md:p-8 shadow-sm border border-gray-100 hover:shadow-md transition-all duration-500 group-hover:-translate-y-1 group-hover:scale-105"
    >
      <!-- Top section with icon and number -->
      <div class="flex items-center justify-between mb-5">
        <div
          class="w-14 h-14 md:w-16 md:h-16 text-white rounded-2xl flex items-center justify-center font-bold text-lg md:text-xl shadow-sm group-hover:scale-110 transition-transform duration-300 relative overflow-hidden"
          :class="iconClass"
          ref="stepIcon"
        >
          <!-- Icon background animation -->
          <div
            class="absolute inset-0 bg-white opacity-0 group-hover:opacity-20 transition-opacity duration-300"
          ></div>
          <component :is="icon" class="w-6 h-6 md:w-8 md:h-8 relative z-10" />
        </div>
        <div
          class="text-2xl md:text-3xl font-bold text-gray-300 group-hover:text-black transition-colors duration-300"
          :class="numberClass"
        >
          {{ stepNumber }}
        </div>
      </div>

      <!-- Content section -->
      <div class="space-y-4">
        <h3
          class="text-xl md:text-2xl font-bold text-black group-hover:text-black transition-colors duration-300 leading-tight"
          :class="titleClass"
        >
          {{ title }}
        </h3>
        <p class="text-gray-600 leading-relaxed text-sm md:text-base">{{ description }}</p>

        <!-- Items list with improved styling -->
        <div class="space-y-2 pt-2">
          <div
            v-for="(item, index) in items"
            :key="index"
            class="flex items-center gap-3 text-sm text-gray-500 group-hover:text-gray-700 transition-colors duration-300"
          >
            <div
              class="w-2 h-2 rounded-full animate-pulse flex-shrink-0"
              :class="itemColor"
              :style="{ animationDelay: `${index * 1500}ms` }"
            ></div>
            <span class="font-medium">{{ item }}</span>
          </div>
        </div>
      </div>

      <!-- Bottom accent line -->
      <div
        class="absolute bottom-0 left-0 right-0 h-1 rounded-b-3xl transition-all duration-500 opacity-0 group-hover:opacity-100"
        :class="accentLineClass"
      ></div>
    </div>
  </div>
</template>

<script setup lang="ts">
import { ref, computed } from 'vue'
import type { Component } from 'vue'

interface Props {
  stepNumber: string
  title: string
  description: string
  items: string[]
  icon: Component
  variant?: 'primary' | 'accent' | 'success' | 'mixed'
}

const props = withDefaults(defineProps<Props>(), {
  variant: 'primary',
})

const processStep = ref<HTMLElement>()
const stepIcon = ref<HTMLElement>()

// Computed classes based on variant
const iconClass = computed(() => {
  switch (props.variant) {
    case 'primary':
      return 'bg-black'
    case 'accent':
      return 'bg-black'
    case 'success':
      return 'bg-black'
    case 'mixed':
      return 'bg-black'
    default:
      return 'bg-black'
  }
})

const numberClass = computed(() => {
  switch (props.variant) {
    case 'primary':
      return 'group-hover:text-black'
    case 'accent':
      return 'group-hover:text-black'
    case 'success':
      return 'group-hover:text-black'
    case 'mixed':
      return 'group-hover:text-black'
    default:
      return 'group-hover:text-black'
  }
})

const titleClass = computed(() => {
  switch (props.variant) {
    case 'primary':
      return 'group-hover:text-black'
    case 'accent':
      return 'group-hover:text-black'
    case 'success':
      return 'group-hover:text-black'
    case 'mixed':
      return 'group-hover:text-black'
    default:
      return 'group-hover:text-black'
  }
})

const itemColor = computed(() => {
  switch (props.variant) {
    case 'primary':
      return 'bg-black'
    case 'accent':
      return 'bg-black'
    case 'success':
      return 'bg-black'
    case 'mixed':
      return 'bg-black'
    default:
      return 'bg-black'
  }
})

const accentLineClass = computed(() => {
  switch (props.variant) {
    case 'primary':
      return 'bg-black'
    case 'accent':
      return 'bg-black'
    case 'success':
      return 'bg-black'
    case 'mixed':
      return 'bg-black'
    default:
      return 'bg-black'
  }
})

defineExpose({
  processStep,
  stepIcon,
})
</script>
