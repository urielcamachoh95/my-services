<template>
  <section class="py-16 bg-white" style="opacity: 1 !important; visibility: visible !important">
    <div class="container-custom">
      <div class="max-w-5xl mx-auto">
        <!-- Client Logos Section -->
        <div class="flex flex-wrap justify-center items-center gap-8 md:gap-12 opacity-60">
          <div
            v-for="(client, index) in clients"
            :key="index"
            class="flex items-center justify-center"
            ref="statRefs"
          >
            <div class="text-center">
              <div class="text-2xl font-bold text-black mb-2">{{ client.name }}</div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
import { ref, computed, onMounted } from 'vue'

const statRefs = ref<HTMLElement[]>([])

// Client logos data - similar to the image reference
const clients = computed(() => [
  { name: 'NATIONAL BANK' },
  { name: 'mattered' },
  { name: 'Coca-Cola' },
  { name: 'Adobe' },
  { name: 'SUBWAY' },
  { name: 'codecademy' },
])

onMounted(() => {
  console.log('StatsSection mounted')
  console.log('statRefs:', statRefs.value)
})

defineExpose({
  statRefs,
})
</script>
