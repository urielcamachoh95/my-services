<template>
  <section class="vapor-section-alt glass-section-alt">
    <div class="vapor-section-content">
      <div class="vapor-section-header">
        <h2 class="vapor-section-title vapor-fade-in" ref="statsTitle">
          Resultados que hablan por sí solos
        </h2>
        <p class="vapor-section-subtitle vapor-fade-in">
          Cada número representa un proyecto exitoso y un cliente satisfecho
        </p>
      </div>

      <div class="vapor-grid-wide grid grid-cols-1 md:grid-cols-3">
        <div v-for="(stat, index) in stats" :key="index" class="group relative stat-card-enhanced">
          <div
            class="glass-card text-center p-8 hover:shadow-lg hover:-translate-y-1 transition-all duration-300"
          >
            <!-- Icon with colored background -->
            <div
              class="w-16 h-16 mx-auto mb-6 rounded-xl flex items-center justify-center stat-icon-bg"
            >
              <component :is="stat.icon" class="w-8 h-8 text-white" />
            </div>

            <!-- Stat number -->
            <div
              class="text-4xl font-bold text-slate-800 mb-3 group-hover:scale-110 transition-transform duration-300"
            >
              {{ stat.value }}
            </div>

            <!-- Stat description -->
            <div class="text-slate-600 leading-relaxed">
              {{ stat.label }}
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
import { ref } from 'vue'
import { CheckCircle, Clock, Code } from 'lucide-vue-next'

const stats = [
  {
    value: '20+',
    label: 'Proyectos Entregados a Tiempo',
    icon: CheckCircle,
  },
  {
    value: '24/7',
    label: 'Soporte Disponible para Emergencias',
    icon: Clock,
  },
  {
    value: '7+',
    label: 'Años Construyendo Soluciones Web',
    icon: Code,
  },
]

const statRefs = ref<(HTMLElement | null)[]>([])
const statsTitle = ref<HTMLElement>()

defineExpose({
  statRefs,
  statsTitle,
})
</script>

<style scoped>
.stat-card-enhanced {
  perspective: 1000px;
}

.stat-icon-bg {
  background: linear-gradient(135deg, #06b6d4, #0891b2);
}

.stat-card-enhanced:nth-child(2) .stat-icon-bg {
  background: linear-gradient(135deg, #0ea5e9, #0284c7);
}

.stat-card-enhanced:nth-child(3) .stat-icon-bg {
  background: linear-gradient(135deg, #8b5cf6, #7c3aed);
}
</style>
