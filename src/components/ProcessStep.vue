<template>
  <div class="group relative vapor-fade-in">
    <div class="glass-card relative overflow-hidden h-full p-6">
      <!-- Subtle background pattern -->
      <div class="absolute inset-0 opacity-5">
        <div class="absolute inset-0 isometric-grid"></div>
      </div>

      <div class="relative z-10">
        <!-- Top section with icon and number -->
        <div class="flex items-center justify-between mb-6">
          <div
            class="w-20 h-20 text-white rounded-2xl flex items-center justify-center font-bold text-xl shadow-medium group-hover:scale-110 transition-all duration-300 relative overflow-hidden"
            :class="iconClass"
            ref="stepIcon"
          >
            <component :is="icon" class="w-10 h-10 relative z-10" />
            <!-- Enhanced glow effect -->
            <div
              class="absolute inset-0 bg-white/20 rounded-2xl blur-sm group-hover:blur-md transition-all duration-300"
            ></div>
          </div>
          <div
            class="text-5xl font-bold text-gray-200 group-hover:text-blue-600 transition-all duration-300 group-hover:scale-110"
            :class="numberClass"
          >
            {{ stepNumber }}
          </div>
        </div>

        <!-- Content section -->
        <div class="space-y-4">
          <h3
            class="heading-sm group-hover:text-blue-600 transition-colors duration-300 leading-tight"
          >
            {{ title }}
          </h3>
          <p class="text-body-md text-gray-600 leading-relaxed">{{ description }}</p>

          <!-- Enhanced items list with improved styling -->
          <div class="space-y-3 pt-4">
            <div
              v-for="(item, index) in items"
              :key="index"
              class="flex items-center gap-3 text-base text-gray-500 group-hover:text-gray-700 transition-all duration-300 group/item"
            >
              <div
                class="w-3 h-3 rounded-full flex-shrink-0 transition-all duration-300 group-hover/item:scale-125"
                :class="itemColor"
              ></div>
              <span class="font-medium">{{ item }}</span>
            </div>
          </div>
        </div>
      </div>

      <!-- Enhanced bottom accent line -->
      <div
        class="absolute bottom-0 left-0 w-0 h-1 rounded-b-2xl transition-all duration-500 group-hover:w-full"
        :class="accentLineClass"
      ></div>

      <!-- Corner accent -->
      <div
        class="absolute top-0 right-0 w-0 h-0 border-l-[20px] border-l-transparent border-t-[20px] border-t-gray-100 group-hover:border-t-blue-100 transition-all duration-300"
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
      return 'bg-blue-500'
    case 'accent':
      return 'bg-purple-500'
    case 'success':
      return 'bg-green-500'
    case 'mixed':
      return 'bg-indigo-500'
    default:
      return 'bg-blue-500'
  }
})

const numberClass = computed(() => {
  switch (props.variant) {
    case 'primary':
      return 'group-hover:text-blue-600'
    case 'accent':
      return 'group-hover:text-purple-600'
    case 'success':
      return 'group-hover:text-green-600'
    case 'mixed':
      return 'group-hover:text-indigo-600'
    default:
      return 'group-hover:text-blue-600'
  }
})

const itemColor = computed(() => {
  switch (props.variant) {
    case 'primary':
      return 'bg-blue-500'
    case 'accent':
      return 'bg-purple-500'
    case 'success':
      return 'bg-green-500'
    case 'mixed':
      return 'bg-indigo-500'
    default:
      return 'bg-blue-500'
  }
})

const accentLineClass = computed(() => {
  switch (props.variant) {
    case 'primary':
      return 'bg-blue-500'
    case 'accent':
      return 'bg-purple-500'
    case 'success':
      return 'bg-green-500'
    case 'mixed':
      return 'bg-indigo-500'
    default:
      return 'bg-blue-500'
  }
})

defineExpose({
  processStep,
  stepIcon,
})
</script>
