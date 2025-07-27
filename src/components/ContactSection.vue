<template>
  <section class="py-20 bg-white">
    <div class="container-custom">
      <div class="max-w-4xl mx-auto text-center">
        <!-- Handshake Icon -->
        <div class="w-20 h-20 mx-auto mb-8 flex items-center justify-center">
          <svg
            class="w-full h-full text-gray-400"
            fill="none"
            stroke="currentColor"
            viewBox="0 0 24 24"
          >
            <path
              stroke-linecap="round"
              stroke-linejoin="round"
              stroke-width="1.5"
              d="M7 11.5V14m0-2.5v-6a1.5 1.5 0 113 0m-3 6a1.5 1.5 0 00-3 0v2a7.5 7.5 0 0015 0v-5a1.5 1.5 0 00-3 0m-6-3V11m0-5.5v-1a1.5 1.5 0 013 0v1m0 0V11m0-5.5a1.5 1.5 0 013 0v3m0 0V11"
            />
          </svg>
        </div>

        <!-- Main Headline -->
        <h2 class="text-4xl md:text-5xl font-bold text-black mb-12" ref="contactTitle">
          {{ title }}
        </h2>

        <!-- Contact Buttons -->
        <div
          class="flex flex-col sm:flex-row gap-4 justify-center items-center"
          ref="contactButtons"
        >
          <a :href="emailButton.href" class="btn-primary text-lg group">
            <svg class="w-5 h-5" fill="none" stroke="currentColor" viewBox="0 0 24 24">
              <path
                stroke-linecap="round"
                stroke-linejoin="round"
                stroke-width="2"
                d="M3 8l7.89 4.26a2 2 0 002.22 0L21 8M5 19h14a2 2 0 002-2V7a2 2 0 00-2-2H5a2 2 0 00-2 2v10a2 2 0 002 2z"
              />
            </svg>
            {{ emailButton.text }}
          </a>
          <a :href="whatsappButton.href" class="btn-secondary text-lg">
            {{ whatsappButton.text }}
          </a>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
import { ref } from 'vue'

interface Button {
  text: string
  href: string
}

interface Props {
  title?: string
  emailButton?: Button
  whatsappButton?: Button
}

withDefaults(defineProps<Props>(), {
  title: '¿Listo para hacer crecer tu negocio?',
  emailButton: () => ({ text: 'Enviar mensaje', href: 'mailto:contacto@urielcamacho.com' }),
  whatsappButton: () => ({ text: 'Llamar ahora', href: 'tel:+1234567890' }),
})

const contactTitle = ref<HTMLElement>()
const contactButtons = ref<HTMLElement>()

defineExpose({
  contactTitle,
  contactButtons,
})
</script>
