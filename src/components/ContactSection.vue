<template>
  <section class="py-20 bg-white px-4 sm:px-6 lg:px-8">
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
          <a
            href="https://wa.me/573001234567?text=Hola%20Uriel,%20me%20interesa%20trabajar%20contigo%20en%20mi%20proyecto"
            target="_blank"
            rel="noopener noreferrer"
            class="btn-primary text-lg group"
          >
            <svg class="w-5 h-5 mr-2" fill="currentColor" viewBox="0 0 24 24">
              <path
                d="M17.472 14.382c-.297-.149-1.758-.867-2.03-.967-.273-.099-.471-.148-.67.15-.197.297-.767.966-.94 1.164-.173.199-.347.223-.644.075-.297-.15-1.255-.463-2.39-1.475-.883-.788-1.48-1.761-1.653-2.059-.173-.297-.018-.458.13-.606.134-.133.298-.347.446-.52.149-.174.198-.298.298-.497.099-.198.05-.371-.025-.52-.075-.149-.669-1.612-.916-2.207-.242-.579-.487-.5-.669-.51-.173-.008-.371-.01-.57-.01-.198 0-.52.074-.792.372-.272.297-1.04 1.016-1.04 2.479 0 1.462 1.065 2.875 1.213 3.074.149.198 2.096 3.2 5.077 4.487.709.306 1.262.489 1.694.625.712.227 1.36.195 1.871.118.571-.085 1.758-.719 2.006-1.413.248-.694.248-1.289.173-1.413-.074-.124-.272-.198-.57-.347m-5.421 7.403h-.004a9.87 9.87 0 01-5.031-1.378l-.361-.214-3.741.982.998-3.648-.235-.374a9.86 9.86 0 01-1.51-5.26c.001-5.45 4.436-9.884 9.888-9.884 2.64 0 5.122 1.03 6.988 2.898a9.825 9.825 0 012.893 6.994c-.003 5.45-4.437 9.884-9.885 9.884m8.413-18.297A11.815 11.815 0 0012.05 0C5.495 0 .16 5.335.157 11.892c0 2.096.547 4.142 1.588 5.945L.057 24l6.305-1.654a11.882 11.882 0 005.683 1.448h.005c6.554 0 11.89-5.335 11.893-11.893A11.821 11.821 0 0020.885 3.488"
              />
            </svg>
            Hablemos por WhatsApp
            <svg
              class="w-5 h-5 group-hover:translate-x-1 transition-transform duration-300"
              fill="none"
              stroke="currentColor"
              viewBox="0 0 24 24"
            >
              <path
                stroke-linecap="round"
                stroke-linejoin="round"
                stroke-width="2"
                d="M10 6H6a2 2 0 00-2 2v10a2 2 0 002 2h10a2 2 0 002-2v-4M14 4h6m0 0v6m0-6L10 14"
              ></path>
            </svg>
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
  whatsappButton?: Button
}

withDefaults(defineProps<Props>(), {
  title: '¿Listo para hacer crecer tu negocio?',
  whatsappButton: () => ({ text: 'Llamar ahora', href: 'tel:+1234567890' }),
})

const contactTitle = ref<HTMLElement>()
const contactButtons = ref<HTMLElement>()

defineExpose({
  contactTitle,
  contactButtons,
})
</script>
