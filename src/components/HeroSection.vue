<template>
  <div class="relative overflow-hidden">
    <div class="vapor-section-content relative z-10">
      <div class="max-w-7xl mx-auto">
        <!-- Main content grid -->
        <div class="vapor-grid-wide grid grid-cols-1 lg:grid-cols-12 items-center">
          <!-- Text content - Wider section -->
          <div class="lg:col-span-8 space-y-8">
            <!-- Title with gradient highlight -->
            <div class="space-y-4">
              <h1 class="heading-xl">
                <span class="text-slate-800">{{ titleHighlight }}</span>
                <br />
                <span
                  class="bg-gradient-to-r from-cyan-500 to-sky-500 bg-clip-text text-transparent"
                >
                  {{ titleSubtext }}
                </span>
              </h1>
            </div>

            <!-- Subtitle and description -->
            <div class="space-y-6">
              <p class="text-body-lg text-slate-600 leading-relaxed">
                {{ subtitle }}
              </p>
              <p class="text-body-md text-slate-500 leading-relaxed">
                {{ description }}
              </p>
            </div>

            <!-- CTA buttons -->
            <div class="flex flex-col sm:flex-row gap-4">
              <a :href="primaryButton.href" class="vapor-btn-primary group">
                <span>{{ primaryButton.text }}</span>
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
                    d="M13 7l5 5m0 0l-5 5m5-5H6"
                  ></path>
                </svg>
              </a>
              <a :href="secondaryButton.href" class="vapor-btn-secondary group">
                <span>{{ secondaryButton.text }}</span>
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
                    d="M13 7l5 5m0 0l-5 5m5-5H6"
                  ></path>
                </svg>
              </a>
            </div>
          </div>

          <!-- Visual element - Narrower section -->
          <div class="lg:col-span-4 relative">
            <!-- Main visual container -->
            <div class="relative">
              <!-- 3D isometric cube -->
              <div class="w-64 h-64 mx-auto transform rotate-45 perspective-1000">
                <div class="w-full h-full transform-style-preserve-3d animate-float">
                  <!-- Front face -->
                  <div
                    class="absolute inset-0 bg-gradient-to-br from-cyan-400 to-sky-400 rounded-2xl shadow-2xl border-4 border-white/20"
                  ></div>
                  <!-- Right face -->
                  <div
                    class="absolute inset-0 bg-gradient-to-br from-cyan-500 to-sky-500 rounded-2xl shadow-2xl transform rotate-y-90 origin-left border-4 border-white/20"
                  ></div>
                  <!-- Top face -->
                  <div
                    class="absolute inset-0 bg-gradient-to-br from-cyan-300 to-sky-300 rounded-2xl shadow-2xl transform rotate-x-90 origin-bottom border-4 border-white/20"
                  ></div>
                </div>
              </div>

              <!-- Floating elements around the cube -->
              <div
                class="absolute top-8 -left-4 w-16 h-16 bg-cyan-100/80 rounded-full animate-blob"
              ></div>
              <div
                class="absolute bottom-8 -right-4 w-12 h-12 bg-sky-100/80 rounded-full animate-blob animation-delay-2000"
              ></div>
              <div
                class="absolute top-1/2 -right-8 w-8 h-8 bg-cyan-200/60 rounded-lg transform rotate-45 animate-blob animation-delay-1000"
              ></div>

              <!-- Floating info cards -->
              <div class="absolute top-4 left-4 glass-card-floating rounded-xl p-3">
                <div class="text-center">
                  <div class="text-lg font-bold text-cyan-600">100%</div>
                  <div class="text-xs text-gray-600">Satisfacción</div>
                </div>
              </div>
              <div class="absolute bottom-4 right-4 glass-card-floating rounded-xl p-3">
                <div class="text-center">
                  <div class="text-lg font-bold text-sky-600">24/7</div>
                  <div class="text-xs text-gray-600">Soporte</div>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
import { ref } from 'vue'

interface Button {
  text: string
  href: string
}

interface Props {
  profileImage?: string
  profileAlt?: string
  name?: string
  titleHighlight?: string
  titleSubtext?: string
  subtitle?: string
  description?: string
  primaryButton?: Button
  secondaryButton?: Button
}

withDefaults(defineProps<Props>(), {
  profileImage:
    'https://images.unsplash.com/photo-1460925895917-afdab827c52f?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1000&q=80',
  profileAlt: 'Uriel Camacho - Desarrollador Web',
  name: 'Uriel Camacho',
  titleHighlight: 'Transformo ideas',
  titleSubtext: 'en aplicaciones web que escalan tu empresa',
  subtitle:
    'Desarrollador web experto en Laravel, WordPress y aplicaciones personalizadas. Construyo sitios web y aplicaciones que ayudan a tu negocio a vender más y trabajar mejor.',
  description:
    'Desde sitios web corporativos hasta e-commerce complejos. Cada proyecto incluye diseño moderno, optimización SEO, integración de pagos y capacitación para tu equipo.',
  primaryButton: () => ({ text: 'Hablemos de tu negocio', href: '#contacto' }),
  secondaryButton: () => ({ text: 'Ver servicios', href: '#servicios' }),
})

const heroImage = ref<HTMLElement>()
const heroTitle = ref<HTMLElement>()
const heroSubtitle = ref<HTMLElement>()
const heroDescription = ref<HTMLElement>()
const heroButtons = ref<HTMLElement>()

// Remove the scrollToServices function since it's no longer needed

defineExpose({
  heroTitle,
  heroSubtitle,
  heroDescription,
  heroButtons,
  heroImage,
})
</script>
