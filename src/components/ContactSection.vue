<template>
  <section class="vapor-section glass-section relative overflow-hidden">
    <!-- Background with glassmorphism effect -->
    <div class="absolute inset-0 glass-bg-accent"></div>
    <div class="absolute inset-0 opacity-10">
      <div class="absolute inset-0 isometric-grid"></div>
    </div>

    <!-- Floating geometric shapes - more subtle -->
    <div
      class="absolute top-20 right-20 w-32 h-32 bg-slate-100/40 rounded-2xl transform rotate-12 animate-blob"
    ></div>
    <div
      class="absolute bottom-20 left-20 w-24 h-24 bg-slate-100/40 rounded-2xl transform -rotate-12 animate-blob animation-delay-2000"
    ></div>

    <div class="vapor-section-content relative z-10">
      <div class="max-w-4xl mx-auto text-center">
        <!-- Enhanced Icon -->
        <div
          class="w-24 h-24 mx-auto mb-8 flex items-center justify-center bg-white rounded-2xl shadow-large relative group border border-slate-200 hover:shadow-xl hover:scale-105 transition-all duration-300"
        >
          <svg
            class="w-14 h-14 text-cyan-600 group-hover:scale-110 transition-transform duration-300"
            fill="none"
            stroke="currentColor"
            viewBox="0 0 24 24"
          >
            <path
              stroke-linecap="round"
              stroke-linejoin="round"
              stroke-width="2"
              d="M8 12h.01M12 12h.01M16 12h.01M21 12c0 4.418-4.03 8-9 8a9.863 9.863 0 01-4.255-.949L3 20l1.395-3.72C3.512 15.042 3 13.574 3 12c0-4.418 4.03-8 9-8s9 3.582 9 8z"
            />
          </svg>
          <!-- Enhanced glow effect -->
          <div
            class="absolute inset-0 bg-cyan-100/20 rounded-2xl blur-sm group-hover:blur-md transition-all duration-300"
          ></div>
        </div>

        <!-- Main Headline -->
        <h2 class="vapor-section-title vapor-fade-in mb-8" ref="contactTitle">
          {{ title }}
        </h2>

        <!-- Description -->
        <p class="vapor-section-subtitle vapor-fade-in mb-12">
          Estoy aquí para escuchar sobre tu proyecto y ver cómo puedo ayudarte. Comencemos con una
          conversación honesta sobre lo que necesitas para hacer crecer tu negocio.
        </p>

        <!-- CTA buttons -->
        <div class="vapor-cta-buttons vapor-slide-up mb-12" ref="contactButtons">
          <a
            :href="whatsappButton.href"
            target="_blank"
            rel="noopener noreferrer"
            class="vapor-btn-primary text-lg group"
          >
            <svg class="w-5 h-5 mr-2" fill="currentColor" viewBox="0 0 24 24">
              <path
                d="M20.52 3.449C18.24 1.245 15.24 0 12.045 0 5.463 0 .104 5.334.101 11.893c0 2.096.547 4.142 1.588 5.945L.057 24l6.305-1.654a11.882 11.882 0 005.683 1.448h.005c6.554 0 11.89-5.335 11.893-11.893A11.821 11.821 0 0020.52 3.449zM12.05 21.49c-1.554 0-3.146-.428-4.5-1.08l-.361-.214-3.75.982.998-3.648-.235-.374a9.86 9.86 0 01-1.51-5.26c.001-5.45 4.436-9.884 9.888-9.884 2.64 0 5.122 1.03 6.988 2.898a9.825 9.825 0 012.893 6.994c-.003 5.45-4.437 9.884-9.885 9.884z"
              />
              <path
                d="M17.472 14.382c-.297-.149-1.758-.867-2.03-.967-.273-.099-.471-.148-.67.15-.197.297-.767.966-.94 1.164-.173.199-.347.223-.644.075-.297-.15-1.255-.463-2.39-1.475-.883-.788-1.48-1.761-1.653-2.059-.173-.297-.018-.458.13-.606.134-.133.298-.347.446-.52.149-.174.198-.298.298-.497.099-.198.05-.371-.025-.52-.075-.149-.669-1.612-.916-2.207-.242-.579-.487-.5-.669-.51-.173-.008-.371-.01-.57-.01-.198 0-.52.074-.792.372-.272.297-1.04 1.016-1.04 2.479 0 1.462 1.065 2.875 1.213 3.074.149.198 2.096 3.2 5.077 4.487.709.306 1.262.489 1.694.625.712.227 1.36.195 1.871.118.571-.085 1.758-.719 2.006-1.413.248-.694.248-1.289.173-1.413-.074-.124-.272-.198-.57-.347"
              />
            </svg>
            {{ whatsappButton.text }}
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
        </div>

        <!-- Enhanced Additional Info -->
        <div class="mt-16 pt-8 border-t border-slate-200 vapor-fade-in">
          <div class="grid grid-cols-1 md:grid-cols-3 gap-8">
            <div class="text-center group">
              <div
                class="w-16 h-16 mx-auto mb-4 bg-gradient-to-br from-cyan-50 to-sky-50 rounded-2xl flex items-center justify-center border border-cyan-200 group-hover:scale-110 transition-transform duration-300"
              >
                <svg
                  class="w-8 h-8 text-cyan-600"
                  fill="none"
                  stroke="currentColor"
                  viewBox="0 0 24 24"
                >
                  <path
                    stroke-linecap="round"
                    stroke-linejoin="round"
                    stroke-width="2"
                    d="M3 8l7.89 4.26a2 2 0 002.22 0L21 8M5 19h14a2 2 0 002-2V7a2 2 0 00-2-2H5a2 2 0 00-2 2v10a2 2 0 002 2z"
                  />
                </svg>
              </div>
              <h3 class="text-lg font-semibold text-slate-800 mb-2">Correo electrónico</h3>
              <p class="text-slate-600">{{ email }}</p>
            </div>

            <div class="text-center group">
              <div
                class="w-16 h-16 mx-auto mb-4 bg-gradient-to-br from-sky-50 to-cyan-50 rounded-2xl flex items-center justify-center border border-sky-200 group-hover:scale-110 transition-transform duration-300"
              >
                <svg class="w-8 h-8 text-sky-600" fill="currentColor" viewBox="0 0 24 24">
                  <path
                    d="M20.447 20.452h-3.554v-5.569c0-1.328-.027-3.037-1.852-3.037-1.853 0-2.136 1.445-2.136 2.939v5.667H9.351V9h3.414v1.561h.046c.477-.9 1.637-1.85 3.37-1.85 3.601 0 4.267 2.37 4.267 5.455v6.286zM5.337 7.433c-1.144 0-2.063-.926-2.063-2.065 0-1.138.92-2.063 2.063-2.063 1.14 0 2.064.925 2.064 2.063 0 1.139-.925 2.065-2.064 2.065zm1.782 13.019H3.555V9h3.564v11.452zM22.225 0H1.771C.792 0 0 .774 0 1.729v20.542C0 23.227.792 24 1.771 24h20.451C23.2 24 24 23.227 24 22.271V1.729C24 .774 23.2 0 22.222 0h.003z"
                  />
                </svg>
              </div>
              <h3 class="text-lg font-semibold text-slate-800 mb-2">LinkedIn</h3>
              <p class="text-slate-600">@urielcamacho</p>
            </div>

            <div class="text-center group">
              <div
                class="w-16 h-16 mx-auto mb-4 bg-gradient-to-br from-violet-50 to-cyan-50 rounded-2xl flex items-center justify-center border border-violet-200 group-hover:scale-110 transition-transform duration-300"
              >
                <svg class="w-8 h-8 text-violet-600" fill="currentColor" viewBox="0 0 24 24">
                  <path
                    d="M12 2.163c3.204 0 3.584.012 4.85.07 3.252.148 4.771 1.691 4.919 4.919.058 1.265.069 1.645.069 4.849 0 3.205-.012 3.584-.069 4.849-.149 3.225-1.664 4.771-4.919 4.919-1.266.058-1.644.07-4.85.07-3.204 0-3.584-.012-4.849-.07-3.26-.149-4.771-1.699-4.919-4.92-.058-1.265-.07-1.644-.07-4.849 0-3.204.013-3.583.07-4.849.149-3.227 1.664-4.771 4.919-4.919 1.266-.057 1.645-.069 4.849-.069zm0-2.163c-3.259 0-3.667.014-4.947.072-4.358.2-6.78 2.618-6.98 6.98-.059 1.281-.073 1.689-.073 4.948 0 3.259.014 3.668.072 4.948.2 4.358 2.618 6.78 6.98 6.98 1.281.058 1.689.072 4.948.072 3.259 0 3.668-.014 4.948-.072 4.354-.2 6.782-2.618 6.979-6.98.059-1.28.073-1.689.073-4.948 0-3.259-.014-3.667-.072-4.947-.196-4.354-2.617-6.78-6.979-6.98-1.281-.059-1.69-.073-4.949-.073zm0 5.838c-3.403 0-6.162 2.759-6.162 6.162s2.759 6.163 6.162 6.163 6.162-2.759 6.162-6.163c0-3.403-2.759-6.162-6.162-6.162zm0 10.162c-2.209 0-4-1.79-4-4 0-2.209 1.791-4 4-4s4 1.791 4 4c0 2.21-1.791 4-4 4zm6.406-11.845c-.796 0-1.441.645-1.441 1.44s.645 1.44 1.441 1.44c.795 0 1.439-.645 1.439-1.44s-.644-1.44-1.439-1.44z"
                  />
                </svg>
              </div>
              <h3 class="text-lg font-semibold text-slate-800 mb-2">Instagram</h3>
              <p class="text-slate-600">@urielcamacho</p>
            </div>
          </div>
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
  email?: string
}

withDefaults(defineProps<Props>(), {
  title: '¿Listo para hacer crecer tu negocio?',
  whatsappButton: () => ({
    text: 'Hablemos por WhatsApp',
    href: 'https://wa.me/+5212212287141?text=Hola%20Uriel,%20me%20interesa%20trabajar%20contigo%20en%20mi%20proyecto',
  }),
  email: 'urielcamachoh95@gmail.com',
})

const contactTitle = ref<HTMLElement>()
const contactButtons = ref<HTMLElement>()

defineExpose({
  contactTitle,
  contactButtons,
})
</script>
