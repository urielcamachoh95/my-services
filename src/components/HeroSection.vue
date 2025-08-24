<template>
  <div class="relative overflow-hidden">
    <div class="vapor-section-content relative z-10">
      <div class="max-w-7xl mx-auto">
        <!-- Main content grid -->
        <div class="vapor-grid-wide grid grid-cols-1 lg:grid-cols-12 items-center">
          <!-- Left content -->
          <div class="lg:col-span-7 space-y-6">
            <h1 class="text-5xl lg:text-6xl font-bold leading-tight">
              <span
                class="text-transparent bg-gradient-to-r from-cyan-500 to-blue-600 bg-clip-text"
              >
                {{ titleHighlight }}
              </span>
              <br />
              <span class="text-slate-900">{{ titleSubtext }}</span>
            </h1>

            <p class="text-base lg:text-lg text-slate-600 leading-tight max-w-xl">
              {{ subtitle }}
            </p>

            <!-- CTA Buttons -->
            <div class="flex flex-col sm:flex-row gap-4 pt-4">
              <a :href="primaryButton.href" class="vapor-btn-primary text-lg group">
                <svg class="w-5 h-5 mr-2" fill="currentColor" viewBox="0 0 24 24">
                  <path
                    d="M20 2H4c-1.1 0-2 .9-2 2v12c0 1.1.9 2 2 2h4l4 4 4-4h4c1.1 0 2-.9 2-2V4c0-1.1-.9-2-2-2z"
                  />
                </svg>
                {{ primaryButton.text }}
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

              <a :href="secondaryButton.href" class="vapor-btn-secondary text-lg group">
                {{ secondaryButton.text }}
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
          </div>

          <!-- Right content -->
          <div class="lg:col-span-5 relative">
            <!-- Main visual element - 3D isometric card -->
            <div class="relative">
              <div
                class="w-80 h-80 mx-auto relative transform rotate-12 hover:rotate-6 transition-transform duration-500"
              >
                <!-- Main card -->
                <div
                  class="w-full h-full bg-gradient-to-br from-cyan-400 to-blue-500 rounded-2xl shadow-2xl flex items-center justify-center relative overflow-hidden"
                >
                  <!-- Geometric patterns -->
                  <div class="absolute inset-0 opacity-20">
                    <div
                      class="absolute top-4 left-4 w-16 h-16 border-2 border-white rounded-lg"
                    ></div>
                    <div
                      class="absolute top-8 right-8 w-8 h-8 border border-white rounded-full"
                    ></div>
                    <div
                      class="absolute bottom-12 left-8 w-12 h-12 border border-white transform rotate-45"
                    ></div>
                    <div class="absolute bottom-8 right-12 w-6 h-6 bg-white rounded-full"></div>
                  </div>

                  <!-- Main content -->
                  <div class="text-center text-white z-10">
                    <div
                      class="w-20 h-20 bg-white/20 backdrop-blur-sm rounded-xl flex items-center justify-center mx-auto mb-4 hover:bg-white/30 hover:scale-105 transition-all duration-300"
                    >
                      <svg
                        class="w-10 h-10 text-white"
                        fill="none"
                        stroke="currentColor"
                        viewBox="0 0 24 24"
                      >
                        <path
                          stroke-linecap="round"
                          stroke-linejoin="round"
                          stroke-width="2"
                          d="M9.75 17L9 20l-1 1h8l-1-1-.75-3M3 13h18M5 17h14a2 2 0 002-2V5a2 2 0 00-2-2H5a2 2 0 00-2 2v10a2 2 0 002 2z"
                        />
                      </svg>
                    </div>
                    <h3 class="text-lg font-semibold">Desarrollo Web</h3>
                    <p class="text-white/80 text-sm">Soluciones personalizadas</p>
                  </div>
                </div>
              </div>

              <!-- Floating info cards -->
              <div
                class="absolute -top-4 -left-4 glass-card rounded-xl p-3 transform -rotate-12 hover:shadow-lg hover:-translate-y-1 transition-all duration-300"
              >
                <div class="text-center">
                  <div class="text-lg font-bold text-cyan-600">100%</div>
                  <div class="text-xs text-slate-600">Compromiso</div>
                </div>
              </div>

              <div
                class="absolute -bottom-4 -right-4 glass-card rounded-xl p-3 transform rotate-12 hover:shadow-lg hover:-translate-y-1 transition-all duration-300"
              >
                <div class="text-center">
                  <div class="text-lg font-bold text-sky-600">20+</div>
                  <div class="text-xs text-slate-600">Proyectos</div>
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
    'Desarrollador web experto en Laravel, WordPress y aplicaciones personalizadas. Construyo sitios web que ayudan a tu negocio a vender más y trabajar mejor. Desde sitios corporativos hasta e-commerce complejos, cada proyecto incluye diseño moderno, optimización SEO y capacitación.',
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
