<template>
  <section class="py-24 bg-white overflow-hidden" id="faq">
    <div class="container mx-auto px-4 sm:px-6 lg:px-8">
      <!-- Section Header -->
      <div class="text-center mb-20">
        <h2 class="text-3xl md:text-4xl lg:text-5xl font-bold text-gray-900 mb-6">
          Información práctica para tu decisión
        </h2>
        <p class="text-lg md:text-xl text-gray-700 max-w-3xl mx-auto">
          Las dudas más comunes que tienen empresarios como tú antes de empezar con su presencia
          web. Te las respondo de manera clara y honesta.
        </p>
      </div>

      <!-- FAQ Accordion -->
      <div class="max-w-4xl mx-auto space-y-4">
        <!-- FAQ Item 1: What makes my work different -->
        <div class="bg-gray-50 rounded-2xl border border-gray-200 overflow-hidden">
          <button
            @click="toggleFAQ(0)"
            class="w-full px-6 py-6 text-left focus:outline-none focus:ring-2 focus:ring-blue-500 focus:ring-inset transition-all duration-200"
            :class="{ 'bg-blue-50 border-blue-200': expandedFAQs[0] }"
          >
            <div class="flex items-center justify-between">
              <h3 class="text-lg font-semibold text-gray-900 pr-4">
                ¿Qué hace diferente mi trabajo?
              </h3>
              <svg
                class="w-6 h-6 text-gray-500 transition-transform duration-200 flex-shrink-0"
                :class="{ 'rotate-45': expandedFAQs[0] }"
                fill="none"
                stroke="currentColor"
                viewBox="0 0 24 24"
              >
                <path
                  stroke-linecap="round"
                  stroke-linejoin="round"
                  stroke-width="2"
                  d="M12 6v6m0 0v6m0-6h6m-6 0H6"
                ></path>
              </svg>
            </div>
          </button>
          <div v-show="expandedFAQs[0]" class="px-6 pb-6">
            <div class="pt-4 border-t border-gray-200">
              <ul class="space-y-3 text-gray-700 leading-relaxed">
                <li class="flex items-start space-x-3">
                  <svg
                    class="w-5 h-5 text-green-500 mt-0.5 flex-shrink-0"
                    fill="currentColor"
                    viewBox="0 0 20 20"
                  >
                    <path
                      fill-rule="evenodd"
                      d="M10 18a8 8 0 100-16 8 8 0 000 16zm3.707-9.293a1 1 0 00-1.414-1.414L9 10.586 7.707 9.293a1 1 0 00-1.414 1.414l2 2a1 1 0 001.414 0l4-4z"
                      clip-rule="evenodd"
                    ></path>
                  </svg>
                  <span>Páginas diseñadas para generar clientes, no solo para verse bien</span>
                </li>
                <li class="flex items-start space-x-3">
                  <svg
                    class="w-5 h-5 text-green-500 mt-0.5 flex-shrink-0"
                    fill="currentColor"
                    viewBox="0 0 20 20"
                  >
                    <path
                      fill-rule="evenodd"
                      d="M10 18a8 8 0 100-16 8 8 0 000 16zm3.707-9.293a1 1 0 00-1.414-1.414L9 10.586 7.707 9.293a1 1 0 00-1.414 1.414l2 2a1 1 0 001.414 0l4-4z"
                      clip-rule="evenodd"
                    ></path>
                  </svg>
                  <span>Pruebo que todo funcione correctamente antes de entregarte</span>
                </li>
                <li class="flex items-start space-x-3">
                  <svg
                    class="w-5 h-5 text-green-500 mt-0.5 flex-shrink-0"
                    fill="currentColor"
                    viewBox="0 0 20 20"
                  >
                    <path
                      fill-rule="evenodd"
                      d="M10 18a8 8 0 100-16 8 8 0 000 16zm3.707-9.293a1 1 0 00-1.414-1.414L9 10.586 7.707 9.293a1 1 0 00-1.414 1.414l2 2a1 1 0 001.414 0l4-4z"
                      clip-rule="evenodd"
                    ></path>
                  </svg>
                  <span>Te enseño a usar y actualizar tu página</span>
                </li>
                <li class="flex items-start space-x-3">
                  <svg
                    class="w-5 h-5 text-green-500 mt-0.5 flex-shrink-0"
                    fill="currentColor"
                    viewBox="0 0 20 20"
                  >
                    <path
                      fill-rule="evenodd"
                      d="M10 18a8 8 0 100-16 8 8 0 000 16zm3.707-9.293a1 1 0 00-1.414-1.414L9 10.586 7.707 9.293a1 1 0 00-1.414 1.414l2 2a1 1 0 001.414 0l4-4z"
                      clip-rule="evenodd"
                    ></path>
                  </svg>
                  <span>Seguimiento del primer mes incluido</span>
                </li>
              </ul>
            </div>
          </div>
        </div>

        <!-- FAQ Item 2: What results can I expect -->
        <div class="bg-gray-50 rounded-2xl border border-gray-200 overflow-hidden">
          <button
            @click="toggleFAQ(1)"
            class="w-full px-6 py-6 text-left focus:outline-none focus:ring-2 focus:ring-blue-500 focus:ring-inset transition-all duration-200"
            :class="{ 'bg-blue-50 border-blue-200': expandedFAQs[1] }"
          >
            <div class="flex items-center justify-between">
              <h3 class="text-lg font-semibold text-gray-900 pr-4">
                ¿Qué tipo de resultados puedo esperar?
              </h3>
              <svg
                class="w-6 h-6 text-gray-500 transition-transform duration-200 flex-shrink-0"
                :class="{ 'rotate-45': expandedFAQs[1] }"
                fill="none"
                stroke="currentColor"
                viewBox="0 0 24 24"
              >
                <path
                  stroke-linecap="round"
                  stroke-linejoin="round"
                  stroke-width="2"
                  d="M12 6v6m0 0v6m0-6h6m-6 0H6"
                ></path>
              </svg>
            </div>
          </button>
          <div v-show="expandedFAQs[1]" class="px-6 pb-6">
            <div class="pt-4 border-t border-gray-200">
              <ul class="space-y-3 text-gray-700 leading-relaxed">
                <li class="flex items-start space-x-3">
                  <svg
                    class="w-5 h-5 text-green-500 mt-0.5 flex-shrink-0"
                    fill="currentColor"
                    viewBox="0 0 20 20"
                  >
                    <path
                      fill-rule="evenodd"
                      d="M10 18a8 8 0 100-16 8 8 0 000 16zm3.707-9.293a1 1 0 00-1.414-1.414L9 10.586 7.707 9.293a1 1 0 00-1.414 1.414l2 2a1 1 0 001.414 0l4-4z"
                      clip-rule="evenodd"
                    ></path>
                  </svg>
                  <span>Más visibilidad: Aparecer cuando te buscan en Google</span>
                </li>
                <li class="flex items-start space-x-3">
                  <svg
                    class="w-5 h-5 text-green-500 mt-0.5 flex-shrink-0"
                    fill="currentColor"
                    viewBox="0 0 20 20"
                  >
                    <path
                      fill-rule="evenodd"
                      d="M10 18a8 8 0 100-16 8 8 0 000 16zm3.707-9.293a1 1 0 00-1.414-1.414L9 10.586 7.707 9.293a1 1 0 00-1.414 1.414l2 2a1 1 0 001.414 0l4-4z"
                      clip-rule="evenodd"
                    ></path>
                  </svg>
                  <span>Más consultas: Formularios y teléfonos que realmente funcionan</span>
                </li>
                <li class="flex items-start space-x-3">
                  <svg
                    class="w-5 h-5 text-green-500 mt-0.5 flex-shrink-0"
                    fill="currentColor"
                    viewBox="0 0 20 20"
                  >
                    <path
                      fill-rule="evenodd"
                      d="M10 18a8 8 0 100-16 8 8 0 000 16zm3.707-9.293a1 1 0 00-1.414-1.414L9 10.586 7.707 9.293a1 1 0 00-1.414 1.414l2 2a1 1 0 001.414 0l4-4z"
                      clip-rule="evenodd"
                    ></path>
                  </svg>
                  <span>Más credibilidad: Página profesional que transmite confianza</span>
                </li>
                <li class="flex items-start space-x-3">
                  <svg
                    class="w-5 h-5 text-green-500 mt-0.5 flex-shrink-0"
                    fill="currentColor"
                    viewBox="0 0 20 20"
                  >
                    <path
                      fill-rule="evenodd"
                      d="M10 18a8 8 0 100-16 8 8 0 000 16zm3.707-9.293a1 1 0 00-1.414-1.414L9 10.586 7.707 9.293a1 1 0 00-1.414 1.414l2 2a1 1 0 001.414 0l4-4z"
                      clip-rule="evenodd"
                    ></path>
                  </svg>
                  <span>Medimos resultados reales: visitantes, consultas, ventas</span>
                </li>
              </ul>
            </div>
          </div>
        </div>

        <!-- FAQ Item 3: How do I know if I need a website -->
        <div class="bg-gray-50 rounded-2xl border border-gray-200 overflow-hidden">
          <button
            @click="toggleFAQ(2)"
            class="w-full px-6 py-6 text-left focus:outline-none focus:ring-2 focus:ring-blue-500 focus:ring-inset transition-all duration-200"
            :class="{ 'bg-blue-50 border-blue-200': expandedFAQs[2] }"
          >
            <div class="flex items-center justify-between">
              <h3 class="text-lg font-semibold text-gray-900 pr-4">
                ¿Cómo sé si necesito una página web?
              </h3>
              <svg
                class="w-6 h-6 text-gray-500 transition-transform duration-200 flex-shrink-0"
                :class="{ 'rotate-45': expandedFAQs[2] }"
                fill="none"
                stroke="currentColor"
                viewBox="0 0 24 24"
              >
                <path
                  stroke-linecap="round"
                  stroke-linejoin="round"
                  stroke-width="2"
                  d="M12 6v6m0 0v6m0-6h6m-6 0H6"
                ></path>
              </svg>
            </div>
          </button>
          <div v-show="expandedFAQs[2]" class="px-6 pb-6">
            <div class="pt-4 border-t border-gray-200">
              <ul class="space-y-3 text-gray-700 leading-relaxed">
                <li class="flex items-start space-x-3">
                  <svg
                    class="w-5 h-5 text-green-500 mt-0.5 flex-shrink-0"
                    fill="currentColor"
                    viewBox="0 0 20 20"
                  >
                    <path
                      fill-rule="evenodd"
                      d="M10 18a8 8 0 100-16 8 8 0 000 16zm3.707-9.293a1 1 0 00-1.414-1.414L9 10.586 7.707 9.293a1 1 0 00-1.414 1.414l2 2a1 1 0 001.414 0l4-4z"
                      clip-rule="evenodd"
                    ></path>
                  </svg>
                  <span>Si tus clientes buscan servicios como el tuyo en internet</span>
                </li>
                <li class="flex items-start space-x-3">
                  <svg
                    class="w-5 h-5 text-green-500 mt-0.5 flex-shrink-0"
                    fill="currentColor"
                    viewBox="0 0 20 20"
                  >
                    <path
                      fill-rule="evenodd"
                      d="M10 18a8 8 0 100-16 8 8 0 000 16zm3.707-9.293a1 1 0 00-1.414-1.414L9 10.586 7.707 9.293a1 1 0 00-1.414 1.414l2 2a1 1 0 001.414 0l4-4z"
                      clip-rule="evenodd"
                    ></path>
                  </svg>
                  <span>Si quieres vender fuera de tu horario de trabajo</span>
                </li>
                <li class="flex items-start space-x-3">
                  <svg
                    class="w-5 h-5 text-green-500 mt-0.5 flex-shrink-0"
                    fill="currentColor"
                    viewBox="0 0 20 20"
                  >
                    <path
                      fill-rule="evenodd"
                      d="M10 18a8 8 0 100-16 8 8 0 000 16zm3.707-9.293a1 1 0 00-1.414-1.414L9 10.586 7.707 9.293a1 1 0 00-1.414 1.414l2 2a1 1 0 001.414 0l4-4z"
                      clip-rule="evenodd"
                    ></path>
                  </svg>
                  <span>Si competidores ya tienen páginas y tú no</span>
                </li>
                <li class="flex items-start space-x-3">
                  <svg
                    class="w-5 h-5 text-green-500 mt-0.5 flex-shrink-0"
                    fill="currentColor"
                    viewBox="0 0 20 20"
                  >
                    <path
                      fill-rule="evenodd"
                      d="M10 18a8 8 0 100-16 8 8 0 000 16zm3.707-9.293a1 1 0 00-1.414-1.414L9 10.586 7.707 9.293a1 1 0 00-1.414 1.414l2 2a1 1 0 001.414 0l4-4z"
                      clip-rule="evenodd"
                    ></path>
                  </svg>
                  <span>Si gastas en publicidad pero no tienes dónde enviar gente</span>
                </li>
              </ul>
            </div>
          </div>
        </div>

        <!-- FAQ Item 4: What happens after it's ready -->
        <div class="bg-gray-50 rounded-2xl border border-gray-200 overflow-hidden">
          <button
            @click="toggleFAQ(3)"
            class="w-full px-6 py-6 text-left focus:outline-none focus:ring-2 focus:ring-blue-500 focus:ring-inset transition-all duration-200"
            :class="{ 'bg-blue-50 border-blue-200': expandedFAQs[3] }"
          >
            <div class="flex items-center justify-between">
              <h3 class="text-lg font-semibold text-gray-900 pr-4">
                ¿Qué pasa después de que esté lista?
              </h3>
              <svg
                class="w-6 h-6 text-gray-500 transition-transform duration-200 flex-shrink-0"
                :class="{ 'rotate-45': expandedFAQs[3] }"
                fill="none"
                stroke="currentColor"
                viewBox="0 0 24 24"
              >
                <path
                  stroke-linecap="round"
                  stroke-linejoin="round"
                  stroke-width="2"
                  d="M12 6v6m0 0v6m0-6h6m-6 0H6"
                ></path>
              </svg>
            </div>
          </button>
          <div v-show="expandedFAQs[3]" class="px-6 pb-6">
            <div class="pt-4 border-t border-gray-200">
              <ul class="space-y-3 text-gray-700 leading-relaxed">
                <li class="flex items-start space-x-3">
                  <svg
                    class="w-5 h-5 text-green-500 mt-0.5 flex-shrink-0"
                    fill="currentColor"
                    viewBox="0 0 20 20"
                  >
                    <path
                      fill-rule="evenodd"
                      d="M10 18a8 8 0 100-16 8 8 0 000 16zm3.707-9.293a1 1 0 00-1.414-1.414L9 10.586 7.707 9.293a1 1 0 00-1.414 1.414l2 2a1 1 0 001.414 0l4-4z"
                      clip-rule="evenodd"
                    ></path>
                  </svg>
                  <span>La página es tuya, no dependes de mí para siempre</span>
                </li>
                <li class="flex items-start space-x-3">
                  <svg
                    class="w-5 h-5 text-green-500 mt-0.5 flex-shrink-0"
                    fill="currentColor"
                    viewBox="0 0 20 20"
                  >
                    <path
                      fill-rule="evenodd"
                      d="M10 18a8 8 0 100-16 8 8 0 000 16zm3.707-9.293a1 1 0 00-1.414-1.414L9 10.586 7.707 9.293a1 1 0 00-1.414 1.414l2 2a1 1 0 001.414 0l4-4z"
                      clip-rule="evenodd"
                    ></path>
                  </svg>
                  <span>Te capacito para hacer cambios básicos</span>
                </li>
                <li class="flex items-start space-x-3">
                  <svg
                    class="w-5 h-5 text-green-500 mt-0.5 flex-shrink-0"
                    fill="currentColor"
                    viewBox="0 0 20 20"
                  >
                    <path
                      fill-rule="evenodd"
                      d="M10 18a8 8 0 100-16 8 8 0 000 16zm3.707-9.293a1 1 0 00-1.414-1.414L9 10.586 7.707 9.293a1 1 0 00-1.414 1.414l2 2a1 1 0 001.414 0l4-4z"
                      clip-rule="evenodd"
                    ></path>
                  </svg>
                  <span>Mantenimiento opcional disponible</span>
                </li>
                <li class="flex items-start space-x-3">
                  <svg
                    class="w-5 h-5 text-green-500 mt-0.5 flex-shrink-0"
                    fill="currentColor"
                    viewBox="0 0 20 20"
                  >
                    <path
                      fill-rule="evenodd"
                      d="M10 18a8 8 0 100-16 8 8 0 000 16zm3.707-9.293a1 1 0 00-1.414-1.414L9 10.586 7.707 9.293a1 1 0 00-1.414 1.414l2 2a1 1 0 001.414 0l4-4z"
                      clip-rule="evenodd"
                    ></path>
                  </svg>
                  <span>Soporte por WhatsApp cuando lo necesites</span>
                </li>
              </ul>
            </div>
          </div>
        </div>

        <!-- FAQ Item 5: How much does it really cost -->
        <div class="bg-gray-50 rounded-2xl border border-gray-200 overflow-hidden">
          <button
            @click="toggleFAQ(4)"
            class="w-full px-6 py-6 text-left focus:outline-none focus:ring-2 focus:ring-blue-500 focus:ring-inset transition-all duration-200"
            :class="{ 'bg-blue-50 border-blue-200': expandedFAQs[4] }"
          >
            <div class="flex items-center justify-between">
              <h3 class="text-lg font-semibold text-gray-900 pr-4">¿Cuánto cuesta realmente?</h3>
              <svg
                class="w-6 h-6 text-gray-500 transition-transform duration-200 flex-shrink-0"
                :class="{ 'rotate-45': expandedFAQs[4] }"
                fill="none"
                stroke="currentColor"
                viewBox="0 0 24 24"
              >
                <path
                  stroke-linecap="round"
                  stroke-linejoin="round"
                  stroke-width="2"
                  d="M12 6v6m0 0v6m0-6h6m-6 0H6"
                ></path>
              </svg>
            </div>
          </button>
          <div v-show="expandedFAQs[4]" class="px-6 pb-6">
            <div class="pt-4 border-t border-gray-200">
              <ul class="space-y-3 text-gray-700 leading-relaxed">
                <li class="flex items-start space-x-3">
                  <svg
                    class="w-5 h-5 text-green-500 mt-0.5 flex-shrink-0"
                    fill="currentColor"
                    viewBox="0 0 20 20"
                  >
                    <path
                      fill-rule="evenodd"
                      d="M10 18a8 8 0 100-16 8 8 0 000 16zm3.707-9.293a1 1 0 00-1.414-1.414L9 10.586 7.707 9.293a1 1 0 00-1.414 1.414l2 2a1 1 0 001.414 0l4-4z"
                      clip-rule="evenodd"
                    ></path>
                  </svg>
                  <span>Página web básica: $15,000 - $25,000 pesos</span>
                </li>
                <li class="flex items-start space-x-3">
                  <svg
                    class="w-5 h-5 text-green-500 mt-0.5 flex-shrink-0"
                    fill="currentColor"
                    viewBox="0 0 20 20"
                  >
                    <path
                      fill-rule="evenodd"
                      d="M10 18a8 8 0 100-16 8 8 0 000 16zm3.707-9.293a1 1 0 00-1.414-1.414L9 10.586 7.707 9.293a1 1 0 00-1.414 1.414l2 2a1 1 0 001.414 0l4-4z"
                      clip-rule="evenodd"
                    ></path>
                  </svg>
                  <span>Tienda online: $25,000 - $45,000 pesos</span>
                </li>
                <li class="flex items-start space-x-3">
                  <svg
                    class="w-5 h-5 text-green-500 mt-0.5 flex-shrink-0"
                    fill="currentColor"
                    viewBox="0 0 20 20"
                  >
                    <path
                      fill-rule="evenodd"
                      d="M10 18a8 8 0 100-16 8 8 0 000 16zm3.707-9.293a1 1 0 00-1.414-1.414L9 10.586 7.707 9.293a1 1 0 00-1.414 1.414l2 2a1 1 0 001.414 0l4-4z"
                      clip-rule="evenodd"
                    ></path>
                  </svg>
                  <span>Sistemas personalizados: Consultar según complejidad</span>
                </li>
                <li class="flex items-start space-x-3">
                  <svg
                    class="w-5 h-5 text-green-500 mt-0.5 flex-shrink-0"
                    fill="currentColor"
                    viewBox="0 0 20 20"
                  >
                    <path
                      fill-rule="evenodd"
                      d="M10 18a8 8 0 100-16 8 8 0 000 16zm3.707-9.293a1 1 0 00-1.414-1.414L9 10.586 7.707 9.293a1 1 0 00-1.414 1.414l2 2a1 1 0 001.414 0l4-4z"
                      clip-rule="evenodd"
                    ></path>
                  </svg>
                  <span>Sin costos ocultos ni sorpresas</span>
                </li>
              </ul>
            </div>
          </div>
        </div>
      </div>

      <!-- CTA Section -->
      <div class="text-center mt-16">
        <div
          class="bg-gradient-to-r from-blue-50 to-indigo-50 rounded-3xl p-8 md:p-12 max-w-4xl mx-auto"
        >
          <h3 class="text-2xl md:text-3xl font-bold text-gray-900 mb-4">¿Tienes otra pregunta?</h3>
          <p class="text-lg text-gray-700 mb-8">
            No te quedes con dudas. Escríbeme por WhatsApp y te respondo en menos de 1 hora. Sin
            compromiso, solo para ayudarte a tomar la mejor decisión.
          </p>
          <a
            href="https://wa.me/+5212212287141?text=Hola%20Uriel,%20tengo%20una%20pregunta%20sobre%20mi%20página%20web"
            target="_blank"
            rel="noopener noreferrer"
            class="inline-flex items-center justify-center px-8 py-4 bg-gradient-to-r from-green-600 to-emerald-600 hover:from-green-700 hover:to-emerald-700 text-white font-semibold text-lg rounded-xl shadow-lg hover:shadow-xl transition-all duration-300 transform hover:-translate-y-1"
          >
            <svg class="w-5 h-5 mr-3" fill="currentColor" viewBox="0 0 24 24">
              <path
                d="M17.472 14.382c-.297-.149-1.758-.867-2.03-.967-.273-.099-.471-.148-.67.15-.197.297-.767.966-.94 1.164-.173.199-.347.223-.644.075-.297-.15-1.255-.463-2.39-1.475-.883-.788-1.48-1.761-1.653-2.059-.173-.297-.018-.458.13-.606.134-.133.298-.347.446-.52.149-.174.198-.298.298-.497.099-.198.05-.371-.025-.52-.075-.149-.669-1.612-.916-2.207-.242-.579-.487-.5-.669-.51-.173-.008-.371-.01-.57-.01-.198 0-.52.074-.792.372-.272.297-1.04 1.016-1.04 2.479 0 1.462 1.065 2.875 1.213 3.074.149.198 2.096 3.2 5.077 4.487.709.306 1.262.489 1.694.625.712.227 1.36.195 1.871.118.571-.085 1.758-.719 2.006-1.413.248-.694.248-1.289.173-1.413-.074-.124-.272-.198-.57-.347m-5.421 7.403h-.004a9.87 9.87 0 01-5.031-1.378l-.361-.214-3.741.982.998-3.648-.235-.374a9.86 9.86 0 01-1.51-5.26c.001-5.45 4.436-9.884 9.888-9.884 2.64 0 5.122 1.03 6.988 2.898a9.825 9.825 0 012.893 6.994c-.003 5.45-4.437 9.884-9.885 9.884m8.413-18.297A11.815 11.815 0 0012.05 0C5.495 0 .16 5.335.157 11.892c0 2.096.547 4.142 1.588 5.945L.057 24l6.305-1.654a11.882 11.882 0 005.683 1.448h.005c6.554 0 11.89-5.335 11.893-11.893A11.821 11.821 0 0020.885 3.488"
              />
            </svg>
            Hacer mi pregunta
          </a>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
import { ref, onMounted } from 'vue'
import { gsap } from 'gsap'

const expandedFAQs = ref([false, false, false, false, false])

const toggleFAQ = (index: number) => {
  // Close all other FAQs
  expandedFAQs.value.forEach((_, i) => {
    if (i !== index) {
      expandedFAQs.value[i] = false
    }
  })

  // Toggle the clicked FAQ
  expandedFAQs.value[index] = !expandedFAQs.value[index]
}

onMounted(() => {
  // Ensure all content is visible by default
  gsap.set('h2, p, .max-w-4xl', {
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
        gsap.set('h2, p, .max-w-4xl', {
          opacity: 1,
          visibility: 'visible',
          y: 0,
          x: 0,
          scale: 1,
        })
      },
    })

    // Set initial states
    gsap.set('h2', { y: 30, opacity: 0 })
    gsap.set('h2 + p', { y: 20, opacity: 0 })
    gsap.set('.max-w-4xl > div', { y: 20, opacity: 0 })

    // Animate section header
    tl.to('h2', { y: 0, opacity: 1, duration: 0.8, ease: 'power2.out' }).to(
      'h2 + p',
      { y: 0, opacity: 1, duration: 0.6, ease: 'power2.out' },
      '-=0.4',
    )

    // Animate FAQ items with stagger
    tl.to(
      '.max-w-4xl > div',
      {
        y: 0,
        opacity: 1,
        duration: 0.6,
        stagger: 0.1,
      },
      '-=0.3',
    )
  } catch (error) {
    // Fallback: ensure everything is visible if GSAP fails
    console.warn('GSAP animation failed, ensuring content visibility:', error)
    gsap.set('h2, p, .max-w-4xl', {
      opacity: 1,
      visibility: 'visible',
      y: 0,
      x: 0,
      scale: 1,
    })
  }
})
</script>

<style scoped>
/* Ensure content is always visible by default */
h2,
p,
.max-w-4xl {
  opacity: 1 !important;
  visibility: visible !important;
  transform: none !important;
}

/* Only apply animations when JavaScript is working */
.js-animations h2,
.js-animations p,
.js-animations .max-w-4xl {
  opacity: 1;
  visibility: visible;
  transform: none;
}

/* FAQ accordion styling */
.bg-gray-50 {
  background-color: rgb(249 250 251);
}

.bg-blue-50 {
  background-color: rgb(239 246 255);
}

.border-blue-200 {
  border-color: rgb(191 219 254);
}

/* Smooth transitions for accordion */
.transition-all {
  transition-property: all;
  transition-timing-function: cubic-bezier(0.4, 0, 0.2, 1);
  transition-duration: 200ms;
}

.transition-transform {
  transition-property: transform;
  transition-timing-function: cubic-bezier(0.4, 0, 0.2, 1);
  transition-duration: 200ms;
}

/* Icon rotation for expand/collapse */
.rotate-45 {
  transform: rotate(45deg);
}

/* Focus styles for accessibility */
button:focus {
  outline: none;
  ring: 2px;
  ring-color: rgb(59 130 246);
  ring-offset: 2px;
}

/* Hover effects */
.bg-gray-50:hover {
  background-color: rgb(243 244 246);
}

/* List item spacing */
.space-y-3 > * + * {
  margin-top: 0.75rem;
}

/* Icon alignment */
.flex.items-start.space-x-3 {
  align-items: flex-start;
}

.flex.items-start.space-x-3 > * + * {
  margin-left: 0.75rem;
}
</style>
