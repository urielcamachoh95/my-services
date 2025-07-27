<template>
  <div class="relative group" ref="testimonialCard">
    <div
      class="rounded-3xl p-8 md:p-12 shadow-sm border border-gray-100 hover:shadow-md transition-all duration-500 group-hover:-translate-y-2 relative overflow-hidden bg-white"
      :class="cardClass"
    >
      <!-- Decorative background pattern -->
      <div
        class="absolute w-32 h-32 rounded-full opacity-10 -translate-y-16"
        :class="decorativeClass"
      ></div>

      <!-- Quote icon -->
      <div class="relative z-10 mb-6">
        <div
          class="w-16 h-16 rounded-2xl flex items-center justify-center shadow-sm group-hover:scale-110 transition-transform duration-300"
          :class="iconClass"
        >
          <svg class="w-8 h-8 text-white" fill="currentColor" viewBox="0 0 24 24">
            <path
              d="M14.017 21v-7.391c0-5.704 3.731-9.57 8.983-10.609l.995 2.151c-2.432.917-3.995 3.638-3.995 5.849h4v10h-9.983zm-14.017 0v-7.391c0-5.704 3.748-9.57 9-10.609l.996 2.151c-2.433.917-3.996 3.638-3.996 5.849h3.983v10h-9.983z"
            />
          </svg>
        </div>
      </div>

      <!-- Testimonial content -->
      <div class="relative z-10 space-y-6">
        <p class="text-lg md:text-xl text-gray-600 leading-relaxed italic">"{{ quote }}"</p>

        <div class="flex items-center gap-4">
          <div
            class="w-12 h-12 rounded-full flex items-center justify-center text-white font-bold text-lg shadow-sm"
            :class="avatarClass"
          >
            {{ avatarEmoji }}
          </div>
          <div>
            <h4 class="font-semibold text-black">{{ authorName }}</h4>
            <p class="text-sm text-gray-600">{{ authorTitle }}</p>
          </div>
        </div>
      </div>

      <!-- Success indicator -->
      <div class="absolute top-6 right-6">
        <div class="w-8 h-8 bg-black rounded-full flex items-center justify-center shadow-sm">
          <svg class="w-4 h-4 text-white" fill="none" stroke="currentColor" viewBox="0 0 24 24">
            <path
              stroke-linecap="round"
              stroke-linejoin="round"
              stroke-width="2"
              d="M5 13l4 4L19 7"
            ></path>
          </svg>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
import { ref, computed } from 'vue'

interface Props {
  quote: string
  authorName: string
  authorTitle: string
  avatarEmoji: string
  variant?: 'primary' | 'accent'
}

const props = withDefaults(defineProps<Props>(), {
  variant: 'primary',
})

const testimonialCard = ref<HTMLElement>()

// Computed classes based on variant
const cardClass = computed(() => {
  return 'bg-white'
})

const decorativeClass = computed(() => {
  return props.variant === 'primary'
    ? 'bg-gray-300 top-0 right-0 translate-x-16'
    : 'bg-gray-300 top-0 left-0 -translate-x-16'
})

const iconClass = computed(() => {
  return 'bg-black'
})

const avatarClass = computed(() => {
  return 'bg-black'
})

defineExpose({
  testimonialCard,
})
</script>
