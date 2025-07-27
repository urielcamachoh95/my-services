<template>
  <section class="py-16 bg-white">
    <div class="container-custom">
      <div class="grid grid-cols-1 md:grid-cols-3 gap-8">
        <div
          v-for="(stat, index) in stats"
          :key="index"
          class="text-center"
          :ref="
            (el) => {
              if (el) statRefs[index] = el as HTMLElement
            }
          "
        >
          <div class="text-4xl font-bold text-black mb-2">{{ stat.value }}</div>
          <div class="text-gray-600">{{ stat.label }}</div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
import { ref } from 'vue'

interface Stat {
  value: string
  label: string
}

interface Props {
  stats?: Stat[]
}

withDefaults(defineProps<Props>(), {
  stats: () => [
    { value: '20+', label: 'Proyectos Completados' },
    { value: '24/7', label: 'Soporte Disponible' },
    { value: '7+', label: 'Años de Experiencia' },
  ],
})

const statRefs = ref<(HTMLElement | null)[]>([])

defineExpose({
  statRefs,
})
</script>
