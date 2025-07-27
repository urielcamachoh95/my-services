<template>
  <section
    :id="sectionId"
    :class="[
      'section-padding',
      backgroundClass,
      { 'relative overflow-hidden': hasBackgroundElements },
    ]"
  >
    <!-- Background decorative elements -->
    <div v-if="hasBackgroundElements" class="absolute inset-0 opacity-5">
      <div
        class="absolute top-20 right-10 w-32 h-32 bg-primary-500 rounded-full blur-3xl animate-pulse"
      ></div>
      <div
        class="absolute bottom-20 left-10 w-40 h-40 bg-accent-500 rounded-full blur-3xl animate-pulse animation-delay-2000"
      ></div>
      <div
        class="absolute top-1/2 right-1/4 w-24 h-24 bg-success-500 rounded-full blur-2xl animate-pulse animation-delay-4000"
      ></div>
    </div>

    <div class="container-custom" :class="{ 'relative z-10': hasBackgroundElements }">
      <div :class="containerClass">
        <slot />
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
interface Props {
  backgroundClass?: string
  containerClass?: string
  hasBackgroundElements?: boolean
  sectionId?: string
}

withDefaults(defineProps<Props>(), {
  backgroundClass: 'bg-white',
  containerClass: 'max-w-5xl mx-auto',
  hasBackgroundElements: false,
  sectionId: undefined,
})
</script>
