<template>
  <section class="py-24 bg-white relative overflow-hidden" id="servicios">
    <!-- Background Elements -->
    <div class="absolute inset-0 pointer-events-none overflow-hidden">
      <!-- Subtle Service Elements -->
      <div class="service-subtle service-subtle-1"></div>
      <div class="service-subtle service-subtle-2"></div>

      <!-- Minimal Grid Pattern -->
      <div class="service-minimal-grid"></div>
    </div>

    <div class="container mx-auto px-4 sm:px-6 lg:px-8 relative z-10">
      <!-- Section Header -->
      <div class="text-center mb-16">
        <h2 class="text-4xl md:text-5xl font-bold text-gray-900 mb-6">
          Servicios que generan resultados reales
        </h2>
        <p class="text-xl text-gray-600 max-w-3xl mx-auto leading-relaxed">
          No solo páginas web bonitas, sino herramientas que realmente te traen más clientes y
          aumentan tus ventas. Cada servicio incluye resultados típicos que puedes esperar.
        </p>
      </div>

      <!-- Carousel Container -->
      <div class="relative max-w-6xl mx-auto">
        <!-- Carousel Container -->
        <div
          ref="carouselContainer"
          class="flex gap-8 transition-transform duration-500 ease-out"
          :style="{ transform: `translateX(-${currentIndex * 100}%)` }"
        >
          <!-- Service Card 1: Effective Web Page -->
          <div class="w-96 flex-shrink-0">
            <div
              class="bg-gradient-to-br from-blue-50 to-indigo-100 rounded-2xl p-6 md:p-8 shadow-lg border border-blue-200 hover:shadow-xl transition-all duration-300 transform hover:-translate-y-1"
            >
              <!-- Icon -->
              <div
                class="w-16 h-16 bg-gradient-to-br from-blue-500 to-indigo-600 rounded-2xl flex items-center justify-center mx-auto mb-6"
              >
                <svg
                  class="w-8 h-8 text-white"
                  fill="none"
                  stroke="currentColor"
                  viewBox="0 0 24 24"
                >
                  <path
                    stroke-linecap="round"
                    stroke-linejoin="round"
                    stroke-width="2"
                    d="M21 12a9 9 0 01-9 9m9-9a9 9 0 00-9-9m9 9H3m9 9a9 9 0 01-9-9m9 9c1.657 0 3-4.03 3-9s-1.343-9-3-9m0 18c-1.657 0-3-4.03-3-9s1.343-9 3-9m-9 9a9 9 0 019-9"
                  />
                </svg>
              </div>

              <!-- Title -->
              <h3 class="text-2xl font-bold text-gray-900 text-center mb-4">PÁGINA WEB EFECTIVA</h3>
              <p class="text-gray-600 text-center mb-6">
                Para empresarios que quieren más clientes locales
              </p>

              <!-- What You Get -->
              <div class="mb-6">
                <h4 class="font-semibold text-gray-900 mb-3">Lo que obtienes:</h4>
                <ul class="space-y-2 text-sm text-gray-600">
                  <li class="flex items-start">
                    <svg
                      class="w-4 h-4 text-green-500 mr-2 mt-0.5 flex-shrink-0"
                      fill="currentColor"
                      viewBox="0 0 20 20"
                    >
                      <path
                        fill-rule="evenodd"
                        d="M16.707 5.293a1 1 0 010 1.414l-8 8a1 1 0 01-1.414 0l-4-4a1 1 0 011.414-1.414L8 12.586l7.293-7.293a1 1 0 011.414 0z"
                        clip-rule="evenodd"
                      />
                    </svg>
                    Página que aparece en Google cuando te buscan
                  </li>
                  <li class="flex items-start">
                    <svg
                      class="w-4 h-4 text-green-500 mr-2 mt-0.5 flex-shrink-0"
                      fill="currentColor"
                      viewBox="0 0 20 20"
                    >
                      <path
                        fill-rule="evenodd"
                        d="M16.707 5.293a1 1 0 010 1.414l-8 8a1 1 0 01-1.414 0l-4-4a1 1 0 011.414-1.414L8 12.586l7.293-7.293a1 1 0 011.414 0z"
                        clip-rule="evenodd"
                      />
                    </svg>
                    Formularios que realmente funcionan
                  </li>
                  <li class="flex items-start">
                    <svg
                      class="w-4 h-4 text-green-500 mr-2 mt-0.5 flex-shrink-0"
                      fill="currentColor"
                      viewBox="0 0 20 20"
                    >
                      <path
                        fill-rule="evenodd"
                        d="M16.707 5.293a1 1 0 010 1.414l-8 8a1 1 0 01-1.414 0l-4-4a1 1 0 011.414-1.414L8 12.586l7.293-7.293a1 1 0 011.414 0z"
                        clip-rule="evenodd"
                      />
                    </svg>
                    Carga rápida (tus clientes no se van)
                  </li>
                  <li class="flex items-start">
                    <svg
                      class="w-4 h-4 text-green-500 mr-2 mt-0.5 flex-shrink-0"
                      fill="currentColor"
                      viewBox="0 0 20 20"
                    >
                      <path
                        fill-rule="evenodd"
                        d="M16.707 5.293a1 1 0 010 1.414l-8 8a1 1 0 01-1.414 0l-4-4a1 1 0 011.414-1.414L8 12.586l7.293-7.293a1 1 0 011.414 0z"
                        clip-rule="evenodd"
                      />
                    </svg>
                    Fácil de actualizar tú mismo
                  </li>
                </ul>
              </div>

              <!-- Results and Info -->
              <div class="bg-white rounded-xl p-4 mb-6">
                <div class="grid grid-cols-2 gap-4 text-center">
                  <div>
                    <p class="text-sm text-gray-600">Resultado típico</p>
                    <p class="font-semibold text-gray-900">3-5 llamadas por semana</p>
                  </div>
                  <div>
                    <p class="text-sm text-gray-600">Tiempo</p>
                    <p class="font-semibold text-gray-900">2-3 semanas</p>
                  </div>
                </div>
                <div class="mt-4 text-center">
                  <p class="text-sm text-gray-600">Inversión</p>
                  <p class="text-2xl font-bold text-blue-600">$500 - $1,000</p>
                </div>
              </div>

              <!-- CTA Button -->
              <button
                @click="openLightbox(0)"
                class="w-full bg-gradient-to-r from-blue-600 to-indigo-600 hover:from-blue-700 hover:to-indigo-700 text-white font-semibold py-3 px-6 rounded-xl transition-all duration-300 transform hover:-translate-y-1 hover:shadow-lg"
              >
                Ver casos de éxito
              </button>
            </div>
          </div>

          <!-- Service Card 2: Online Store -->
          <div class="w-96 flex-shrink-0">
            <div
              class="bg-gradient-to-br from-green-50 to-emerald-100 rounded-2xl p-6 md:p-8 shadow-lg border border-green-200 hover:shadow-xl transition-all duration-300 transform hover:-translate-y-1"
            >
              <!-- Icon -->
              <div
                class="w-16 h-16 bg-gradient-to-br from-green-500 to-emerald-600 rounded-2xl flex items-center justify-center mx-auto mb-6"
              >
                <svg
                  class="w-8 h-8 text-white"
                  fill="none"
                  stroke="currentColor"
                  viewBox="0 0 24 24"
                >
                  <path
                    stroke-linecap="round"
                    stroke-linejoin="round"
                    stroke-width="2"
                    d="M16 11V7a4 4 0 00-8 0v4M5 9h14l1 12H4L5 9z"
                  />
                </svg>
              </div>

              <!-- Title -->
              <h3 class="text-2xl font-bold text-gray-900 text-center mb-4">
                TIENDA ONLINE QUE VENDE
              </h3>
              <p class="text-gray-600 text-center mb-6">
                Para productos o servicios que puedes enviar
              </p>

              <!-- What You Get -->
              <div class="mb-6">
                <h4 class="font-semibold text-gray-900 mb-3">Lo que obtienes:</h4>
                <ul class="space-y-2 text-sm text-gray-600">
                  <li class="flex items-start">
                    <svg
                      class="w-4 h-4 text-green-500 mr-2 mt-0.5 flex-shrink-0"
                      fill="currentColor"
                      viewBox="0 0 20 20"
                    >
                      <path
                        fill-rule="evenodd"
                        d="M16.707 5.293a1 1 0 010 1.414l-8 8a1 1 0 01-1.414 0l-4-4a1 1 0 011.414-1.414L8 12.586l7.293-7.293a1 1 0 011.414 0z"
                        clip-rule="evenodd"
                      />
                    </svg>
                    Catálogo profesional de tus productos
                  </li>
                  <li class="flex items-start">
                    <svg
                      class="w-4 h-4 text-green-500 mr-2 mt-0.5 flex-shrink-0"
                      fill="currentColor"
                      viewBox="0 0 20 20"
                    >
                      <path
                        fill-rule="evenodd"
                        d="M16.707 5.293a1 1 0 010 1.414l-8 8a1 1 0 01-1.414 0l-4-4a1 1 0 011.414-1.414L8 12.586l7.293-7.293a1 1 0 011.414 0z"
                        clip-rule="evenodd"
                      />
                    </svg>
                    Cobro en línea con tarjeta
                  </li>
                  <li class="flex items-start">
                    <svg
                      class="w-4 h-4 text-green-500 mr-2 mt-0.5 flex-shrink-0"
                      fill="currentColor"
                      viewBox="0 0 20 20"
                    >
                      <path
                        fill-rule="evenodd"
                        d="M16.707 5.293a1 1 0 010 1.414l-8 8a1 1 0 01-1.414 0l-4-4a1 1 0 011.414-1.414L8 12.586l7.293-7.293a1 1 0 011.414 0z"
                        clip-rule="evenodd"
                      />
                    </svg>
                    Gestión de pedidos e inventario
                  </li>
                  <li class="flex items-start">
                    <svg
                      class="w-4 h-4 text-green-500 mr-2 mt-0.5 flex-shrink-0"
                      fill="currentColor"
                      viewBox="0 0 20 20"
                    >
                      <path
                        fill-rule="evenodd"
                        d="M16.707 5.293a1 1 0 010 1.414l-8 8a1 1 0 01-1.414 0l-4-4a1 1 0 011.414-1.414L8 12.586l7.293-7.293a1 1 0 011.414 0z"
                        clip-rule="evenodd"
                      />
                    </svg>
                    Conexión con redes sociales
                  </li>
                </ul>
              </div>

              <!-- Results and Info -->
              <div class="bg-white rounded-xl p-4 mb-6">
                <div class="grid grid-cols-2 gap-4 text-center">
                  <div>
                    <p class="text-sm text-gray-600">Resultado típico</p>
                    <p class="font-semibold text-gray-900">Ventas 24/7 sin estar presente</p>
                  </div>
                  <div>
                    <p class="text-sm text-gray-600">Tiempo</p>
                    <p class="font-semibold text-gray-900">3-4 semanas</p>
                  </div>
                </div>
                <div class="mt-4 text-center">
                  <p class="text-sm text-gray-600">Inversión</p>
                  <p class="text-2xl font-bold text-green-600">$2,500 - $4,000</p>
                </div>
              </div>

              <!-- CTA Button -->
              <button
                @click="openLightbox(1)"
                class="w-full bg-gradient-to-r from-green-600 to-emerald-600 hover:from-green-700 hover:to-emerald-700 text-white font-semibold py-3 px-6 rounded-xl transition-all duration-300 transform hover:-translate-y-1 hover:shadow-lg"
              >
                Ver casos de éxito
              </button>
            </div>
          </div>

          <!-- Service Card 3: Business Automation -->
          <div class="w-96 flex-shrink-0">
            <div
              class="bg-gradient-to-br from-purple-50 to-pink-100 rounded-2xl p-6 md:p-8 shadow-lg border border-purple-200 hover:shadow-xl transition-all duration-300 transform hover:-translate-y-1"
            >
              <!-- Icon -->
              <div
                class="w-16 h-16 bg-gradient-to-br from-purple-500 to-pink-600 rounded-2xl flex items-center justify-center mx-auto mb-6"
              >
                <svg
                  class="w-8 h-8 text-white"
                  fill="none"
                  stroke="currentColor"
                  viewBox="0 0 24 24"
                >
                  <path
                    stroke-linecap="round"
                    stroke-linejoin="round"
                    stroke-width="2"
                    d="M13 10V3L4 14h7v7l9-11h-7z"
                  />
                </svg>
              </div>

              <!-- Title -->
              <h3 class="text-2xl font-bold text-gray-900 text-center mb-4">
                AUTOMATIZACIÓN DE NEGOCIO
              </h3>
              <p class="text-gray-600 text-center mb-6">
                Para negocios establecidos que crecen rápido
              </p>

              <!-- What You Get -->
              <div class="mb-6">
                <h4 class="font-semibold text-gray-900 mb-3">Lo que obtienes:</h4>
                <ul class="space-y-2 text-sm text-gray-600">
                  <li class="flex items-start">
                    <svg
                      class="w-4 h-4 text-green-500 mr-2 mt-0.5 flex-shrink-0"
                      fill="currentColor"
                      viewBox="0 0 20 20"
                    >
                      <path
                        fill-rule="evenodd"
                        d="M16.707 5.293a1 1 0 010 1.414l-8 8a1 1 0 01-1.414 0l-4-4a1 1 0 011.414-1.414L8 12.586l7.293-7.293a1 1 0 011.414 0z"
                        clip-rule="evenodd"
                      />
                    </svg>
                    Sistema de citas automatizado
                  </li>
                  <li class="flex items-start">
                    <svg
                      class="w-4 h-4 text-green-500 mr-2 mt-0.5 flex-shrink-0"
                      fill="currentColor"
                      viewBox="0 0 20 20"
                    >
                      <path
                        fill-rule="evenodd"
                        d="M16.707 5.293a1 1 0 010 1.414l-8 8a1 1 0 01-1.414 0l-4-4a1 1 0 011.414-1.414L8 12.586l7.293-7.293a1 1 0 011.414 0z"
                        clip-rule="evenodd"
                      />
                    </svg>
                    Gestión de inventario inteligente
                  </li>
                  <li class="flex items-start">
                    <svg
                      class="w-4 h-4 text-green-500 mr-2 mt-0.5 flex-shrink-0"
                      fill="currentColor"
                      viewBox="0 0 20 20"
                    >
                      <path
                        fill-rule="evenodd"
                        d="M16.707 5.293a1 1 0 010 1.414l-8 8a1 1 0 01-1.414 0l-4-4a1 1 0 011.414-1.414L8 12.586l7.293-7.293a1 1 0 011.414 0z"
                        clip-rule="evenodd"
                      />
                    </svg>
                    Reportes automáticos de ventas
                  </li>
                  <li class="flex items-start">
                    <svg
                      class="w-4 h-4 text-green-500 mr-2 mt-0.5 flex-shrink-0"
                      fill="currentColor"
                      viewBox="0 0 20 20"
                    >
                      <path
                        fill-rule="evenodd"
                        d="M16.707 5.293a1 1 0 010 1.414l-8 8a1 1 0 01-1.414 0l-4-4a1 1 0 011.414-1.414L8 12.586l7.293-7.293a1 1 0 011.414 0z"
                        clip-rule="evenodd"
                      />
                    </svg>
                    Integración con WhatsApp Business
                  </li>
                </ul>
              </div>

              <!-- Results and Info -->
              <div class="bg-white rounded-xl p-4 mb-6">
                <div class="grid grid-cols-2 gap-4 text-center">
                  <div>
                    <p class="text-sm text-gray-600">Resultado típico</p>
                    <p class="font-semibold text-gray-900">Ahorro de 15-20h por semana</p>
                  </div>
                  <div>
                    <p class="text-sm text-gray-600">Tiempo</p>
                    <p class="font-semibold text-gray-900">4-6 semanas</p>
                  </div>
                </div>
                <div class="mt-4 text-center">
                  <p class="text-sm text-gray-600">Inversión</p>
                  <p class="text-2xl font-bold text-purple-600">Consultar precio</p>
                </div>
              </div>

              <!-- CTA Button -->
              <button
                @click="openLightbox(2)"
                class="w-full bg-gradient-to-r from-purple-600 to-pink-600 hover:from-purple-700 hover:to-pink-700 text-white font-semibold py-3 px-6 rounded-xl transition-all duration-300 transform hover:-translate-y-1 hover:shadow-lg"
              >
                Ver casos de éxito
              </button>
            </div>
          </div>
        </div>

        <!-- Navigation Dots -->
        <div class="flex justify-center mt-8 space-x-2">
          <button
            v-for="(_, index) in 3"
            :key="index"
            @click="goToSlide(index)"
            :class="[
              'w-3 h-3 rounded-full transition-all duration-300',
              currentIndex === index ? 'bg-blue-600 scale-125' : 'bg-gray-300 hover:bg-gray-400',
            ]"
          ></button>
        </div>

        <!-- Navigation Arrows -->
        <button
          @click="previousSlide"
          class="absolute left-0 top-1/2 transform -translate-y-1/2 -translate-x-12 bg-white hover:bg-gray-50 text-gray-600 hover:text-gray-900 p-3 rounded-full shadow-lg border border-gray-200 transition-all duration-300 hover:shadow-xl"
        >
          <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24">
            <path
              stroke-linecap="round"
              stroke-linejoin="round"
              stroke-width="2"
              d="M15 19l-7-7 7-7"
            />
          </svg>
        </button>
        <button
          @click="nextSlide"
          class="absolute right-0 top-1/2 transform -translate-y-1/2 translate-x-12 bg-white hover:bg-gray-50 text-gray-600 hover:text-gray-900 p-3 rounded-full shadow-lg border border-gray-200 transition-all duration-300 hover:shadow-xl"
        >
          <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24">
            <path
              stroke-linecap="round"
              stroke-linejoin="round"
              stroke-width="2"
              d="M9 5l7 7-7 7"
            />
          </svg>
        </button>
      </div>
    </div>

    <!-- Lightbox Modal -->
    <div
      v-if="showLightbox"
      @click="closeLightbox"
      class="fixed inset-0 bg-black bg-opacity-75 flex items-center justify-center z-50 p-4"
    >
      <div
        @click.stop
        class="bg-white rounded-3xl p-8 max-w-2xl w-full max-h-[90vh] overflow-y-auto"
      >
        <div class="flex justify-between items-start mb-6">
          <h3 class="text-3xl font-bold text-gray-900">
            {{ serviceDetails[currentServiceIndex].title }}
          </h3>
          <button
            @click="closeLightbox"
            class="text-gray-400 hover:text-gray-600 transition-colors"
          >
            <svg class="w-8 h-8" fill="none" stroke="currentColor" viewBox="0 0 24 24">
              <path
                stroke-linecap="round"
                stroke-linejoin="round"
                stroke-width="2"
                d="M6 18L18 6M6 6l12 12"
              />
            </svg>
          </button>
        </div>

        <div class="space-y-6">
          <div>
            <h4 class="text-xl font-semibold text-gray-900 mb-3">¿Qué incluye?</h4>
            <ul class="space-y-2">
              <li
                v-for="feature in serviceDetails[currentServiceIndex].features"
                :key="feature"
                class="flex items-start"
              >
                <svg
                  class="w-5 h-5 text-green-500 mr-3 mt-0.5 flex-shrink-0"
                  fill="currentColor"
                  viewBox="0 0 20 20"
                >
                  <path
                    fill-rule="evenodd"
                    d="M16.707 5.293a1 1 0 010 1.414l-8 8a1 1 0 01-1.414 0l-4-4a1 1 0 011.414-1.414L8 12.586l7.293-7.293a1 1 0 011.414 0z"
                    clip-rule="evenodd"
                  />
                </svg>
                {{ feature }}
              </li>
            </ul>
          </div>

          <div class="bg-gray-50 rounded-2xl p-6">
            <h4 class="text-xl font-semibold text-gray-900 mb-3">Resultados típicos</h4>
            <p class="text-gray-600">{{ serviceDetails[currentServiceIndex].results }}</p>
          </div>

          <div class="bg-blue-50 rounded-2xl p-6">
            <h4 class="text-xl font-semibold text-blue-900 mb-3">¿Por qué funciona?</h4>
            <p class="text-blue-800">{{ serviceDetails[currentServiceIndex].whyItWorks }}</p>
          </div>

          <div class="text-center">
            <a
              href="https://wa.me/+5212212287141?text=Hola%20Uriel,%20me%20interesa%20el%20servicio%20de%20{{ encodeURIComponent(serviceDetails[currentServiceIndex].title) }}"
              target="_blank"
              rel="noopener noreferrer"
              class="inline-flex items-center justify-center px-8 py-4 bg-gradient-to-r from-green-600 to-emerald-600 hover:from-green-700 hover:to-emerald-700 text-white font-semibold text-lg rounded-xl shadow-lg hover:shadow-xl transition-all duration-300 transform hover:-translate-y-1"
            >
              <svg class="w-5 h-5 mr-3" fill="currentColor" viewBox="0 0 24 24">
                <path
                  d="M17.472 14.382c-.297-.149-1.758-.867-2.03-.967-.273-.099-.471-.148-.67.15-.197.297-.767.966-.94 1.164-.173.199-.347.223-.644.075-.297-.15-1.255-.463-2.39-1.475-.883-.788-1.48-1.761-1.653-2.059-.173-.297-.018-.458.13-.606.134-.133.298-.347.446-.52.149-.174.198-.298.298-.497.099-.198.05-.371-.025-.52-.075-.149-.669-1.612-.916-2.207-.242-.579-.487-.5-.669-.51-.173-.008-.371-.01-.57-.01-.198 0-.52.074-.792.372-.272.297-1.04 1.016-1.04 2.479 0 1.462 1.065 2.875 1.213 3.074.149.198 2.096 3.2 5.077 4.487.709.306 1.262.489 1.694.625.712.227 1.36.195 1.871.118.571-.085 1.758-.719 2.006-1.413.248-.694.248-1.289.173-1.413-.074-.124-.272-.198-.57-.347m-5.421 7.403h-.004a9.87 9.87 0 01-5.031-1.378l-.361-.214-3.741.982.998-3.648-.235-.374a9.86 9.86 0 01-1.51-5.26c.001-5.45 4.436-9.884 9.888-9.884 2.64 0 5.122 1.03 6.988 2.898a9.825 9.825 0 012.893 6.994c-.003 5.45-4.437 9.884-9.885 9.884m8.413-18.297A11.815 11.815 0 0012.05 0C5.495 0 .16 5.335.157 11.892c0 2.096.547 4.142 1.588 5.945L.057 24l6.305-1.654a11.882 11.882 0 005.683 1.448h.005c6.554 0 11.89-5.335 11.893-11.893A11.821 11.821 0 0020.885 3.488"
                />
              </svg>
              Empezar este proyecto
            </a>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
import { ref, onMounted, onUnmounted } from 'vue'
import { gsap } from 'gsap'

// Component state
const currentIndex = ref(0)
const showLightbox = ref(false)
const currentServiceIndex = ref(0)
const carouselContainer = ref<HTMLElement | null>(null)

// Auto-play functionality
let autoPlayInterval: number | null = null

// Service details for lightbox
const serviceDetails = [
  {
    title: 'PÁGINA WEB EFECTIVA',
    features: [
      'Diseño responsive optimizado para móviles',
      'SEO básico para aparecer en Google',
      'Formularios de contacto funcionales',
      'Panel de administración fácil de usar',
      'Hosting y dominio incluidos por 1 año',
      'Capacitación para usar tu página web',
    ],
    results:
      'Los clientes típicos reciben 3-5 consultas nuevas por semana desde su página web, con un incremento del 40-60% en clientes locales.',
    whyItWorks:
      'Las páginas web profesionales generan confianza en los clientes. Cuando alguien busca tu servicio en Google y encuentra una página bien diseñada, es más probable que te contacte.',
  },
  {
    title: 'TIENDA ONLINE QUE VENDE',
    features: [
      'Catálogo de productos con imágenes profesionales',
      'Sistema de pagos seguro con tarjetas',
      'Gestión de inventario automática',
      'Sistema de pedidos integrado',
      'Conexión con WhatsApp Business',
      'Reportes de ventas en tiempo real',
    ],
    results:
      'Las tiendas online generan ventas 24/7, permitiendo a los clientes comprar en cualquier momento, incluso fuera del horario de trabajo.',
    whyItWorks:
      'Los clientes modernos prefieren comprar online por conveniencia. Una tienda profesional reduce la fricción de compra y aumenta las conversiones.',
  },
  {
    title: 'AUTOMATIZACIÓN DE NEGOCIO',
    features: [
      'Sistema de citas automatizado',
      'Gestión de inventario inteligente',
      'Reportes automáticos de ventas',
      'Integración con WhatsApp Business',
      'Sistema de recordatorios automáticos',
      'Dashboard para monitorear tu negocio',
    ],
    results:
      'Los sistemas de automatización ahorran 15-20 horas por semana en tareas repetitivas, permitiendo enfocarse en el crecimiento del negocio.',
    whyItWorks:
      'La automatización reduce errores humanos y mejora la eficiencia operativa. Los clientes reciben un servicio más consistente y profesional.',
  },
]

// Navigation functions
const goToSlide = (index: number) => {
  currentIndex.value = index
}

const nextSlide = () => {
  currentIndex.value = (currentIndex.value + 1) % 3
}

const previousSlide = () => {
  currentIndex.value = currentIndex.value === 0 ? 2 : currentIndex.value - 1
}

// Lightbox functions
const openLightbox = (index: number) => {
  currentServiceIndex.value = index
  showLightbox.value = true
}

const closeLightbox = () => {
  showLightbox.value = false
}

// Auto-play functionality
const startAutoPlay = () => {
  autoPlayInterval = setInterval(() => {
    nextSlide()
  }, 5000)
}

const stopAutoPlay = () => {
  if (autoPlayInterval) {
    clearInterval(autoPlayInterval)
    autoPlayInterval = null
  }
}

onMounted(() => {
  // Ensure all content is visible by default
  gsap.set('.text-center, .grid, .flex, .relative', {
    opacity: 1,
    visibility: 'visible',
    y: 0,
    x: 0,
    scale: 1,
  })

  // Only animate if GSAP is working properly
  try {
    const tl = gsap.timeline({
      onComplete: () => {
        // Ensure everything is visible after animation
        gsap.set('.text-center, .grid, .flex, .relative', {
          opacity: 1,
          visibility: 'visible',
          y: 0,
          x: 0,
          scale: 1,
        })
      },
    })

    // Set initial states
    gsap.set('.text-center', { y: 30, opacity: 0 })
    gsap.set('.grid', { y: 20, opacity: 0 })
    gsap.set('.flex', { y: 30, opacity: 0 })
    gsap.set('.relative', { y: 20, opacity: 0 })

    // Animate content
    tl.to('.text-center', { y: 0, opacity: 1, duration: 0.8, ease: 'power2.out' })
      .to('.grid', { y: 0, opacity: 1, duration: 0.6, ease: 'power2.out' }, '-=0.4')
      .to('.flex', { y: 0, opacity: 1, duration: 0.6, ease: 'power2.out' }, '-=0.3')
      .to('.relative', { y: 0, opacity: 1, duration: 0.6, ease: 'power2.out' }, '-=0.4')

    // Animate service elements
    animateServiceElements()
  } catch (error) {
    // Fallback: ensure everything is visible if GSAP fails
    console.warn('GSAP animation failed, ensuring content visibility:', error)
    gsap.set('.text-center, .grid, .flex, .relative', {
      opacity: 1,
      visibility: 'visible',
      y: 0,
      x: 0,
      scale: 1,
    })
  }

  // Start auto-play
  startAutoPlay()

  // Pause auto-play on hover
  if (carouselContainer.value) {
    carouselContainer.value.addEventListener('mouseenter', stopAutoPlay)
    carouselContainer.value.addEventListener('mouseleave', startAutoPlay)
  }
})

onUnmounted(() => {
  stopAutoPlay()
})

const animateServiceElements = () => {
  // Animate subtle elements with very gentle movements
  gsap.to('.service-subtle-1', {
    y: -20,
    duration: 25,
    repeat: -1,
    yoyo: true,
    ease: 'power1.inOut',
  })

  gsap.to('.service-subtle-2', {
    y: 25,
    duration: 30,
    repeat: -1,
    yoyo: true,
    ease: 'power1.inOut',
    delay: 12,
  })
}
</script>

<style scoped>
/* Ensure content is always visible by default */
.text-center,
.grid,
.flex,
.relative {
  opacity: 1 !important;
  visibility: visible !important;
  transform: none !important;
}

/* New Subtle Service Background Elements */
.service-subtle {
  position: absolute;
  border-radius: 50%;
  background: radial-gradient(circle, rgba(147, 51, 234, 0.05) 0%, transparent 70%);
  filter: blur(2px);
}

.service-subtle-1 {
  top: 25%;
  left: 10%;
  width: 180px;
  height: 180px;
}

.service-subtle-2 {
  bottom: 20%;
  right: 15%;
  width: 150px;
  height: 150px;
}

.service-minimal-grid {
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background-image:
    linear-gradient(90deg, rgba(147, 51, 234, 0.015) 1px, transparent 1px),
    linear-gradient(0deg, rgba(147, 51, 234, 0.015) 1px, transparent 1px);
  background-size: 80px 80px;
  transform: perspective(1200px) rotateX(60deg) scale(2.2);
  transform-origin: center center;
}

/* Responsive adjustments */
@media (max-width: 768px) {
  .service-subtle {
    display: none;
  }

  .service-minimal-grid {
    transform: perspective(600px) rotateX(60deg) scale(1.5);
  }
}
</style>
