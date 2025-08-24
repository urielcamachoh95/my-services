<template>
  <div class="max-w-5xl mx-auto">
    <h2 class="text-4xl md:text-5xl font-bold text-black text-center mb-16" ref="successTitle">
      {{ title }}
    </h2>

    <!-- Navigation arrows -->
    <div class="flex justify-center items-center gap-4 mb-8">
      <button
        @click="previousCase"
        class="w-12 h-12 bg-white rounded-full shadow-sm border border-cyan-200 flex items-center justify-center hover:bg-cyan-50 transition-colors duration-300 group"
        :class="{ 'opacity-50 cursor-not-allowed': currentCase === 0 }"
      >
        <svg
          class="w-6 h-6 text-cyan-600 group-hover:text-cyan-700 transition-colors"
          fill="none"
          stroke="currentColor"
          viewBox="0 0 24 24"
        >
          <path
            stroke-linecap="round"
            stroke-linejoin="round"
            stroke-width="2"
            d="M15 19l-7-7 7-7"
          ></path>
        </svg>
      </button>

      <div class="flex gap-2">
        <div
          v-for="(_, index) in cases"
          :key="index"
          class="w-3 h-3 rounded-full transition-all duration-300 cursor-pointer"
          :class="currentCase === index ? 'bg-cyan-500' : 'bg-cyan-200'"
          @click="goToCase(index)"
        ></div>
      </div>

      <button
        @click="nextCase"
        class="w-12 h-12 bg-white rounded-full shadow-sm border border-cyan-200 flex items-center justify-center hover:bg-cyan-50 transition-colors duration-300 group"
        :class="{ 'opacity-50 cursor-not-allowed': currentCase === cases.length - 1 }"
      >
        <svg
          class="w-6 h-6 text-cyan-600 group-hover:text-cyan-700 transition-colors"
          fill="none"
          stroke="currentColor"
          viewBox="0 0 24 24"
        >
          <path
            stroke-linecap="round"
            stroke-linejoin="round"
            stroke-width="2"
            d="M9 5l7 7-7 7"
          ></path>
        </svg>
      </button>
    </div>

    <!-- Cases container -->
    <div class="relative overflow-hidden" ref="casesContainer">
      <SuccessCase
        v-for="(caseData, index) in cases"
        :key="index"
        :title="caseData.title"
        :description="caseData.description"
        :image="caseData.image"
        :image-alt="caseData.imageAlt"
        :features="caseData.features"
        :tags="caseData.tags"
        :stats="caseData.stats"
        :is-active="currentCase === index"
        ref="caseRefs"
      />
    </div>
  </div>
</template>

<script setup lang="ts">
import { ref, computed } from 'vue'
import SuccessCase from './SuccessCase.vue'
import CheckSmallIcon from './icons/CheckSmallIcon.vue'
import TrendingUpIcon from './icons/TrendingUpIcon.vue'

interface Props {
  title?: string
}

withDefaults(defineProps<Props>(), {
  title: 'Casos de éxito',
})

const currentCase = ref(0)
const successTitle = ref<HTMLElement>()
const casesContainer = ref<HTMLElement>()
const caseRefs = ref<HTMLElement[]>([])

// Carousel functions
const nextCase = () => {
  if (currentCase.value < cases.value.length - 1) {
    currentCase.value++
  }
}

const previousCase = () => {
  if (currentCase.value > 0) {
    currentCase.value--
  }
}

const goToCase = (index: number) => {
  currentCase.value = index
}

// Cases data
const cases = computed(() => [
  {
    title: 'Sitio web de reservas para cabañas en Atlixco, Puebla',
    description:
      'Después de mucho tiempo queriendo lanzar su sitio, una empresa de cabañas en Atlixco confió en mí para crear una plataforma donde pudieran recibir reservaciones directamente.',
    image: '/my-services/images/villas-arvem.png',
    imageAlt: 'Cabañas en Atlixco - Sitio web de reservas',
    features: [
      {
        text: 'Desarrollé el sitio en WordPress con un sistema de reservas personalizado, incluyendo calendario, formularios y notificaciones por correo.',
        icon: CheckSmallIcon,
        iconBgClass: 'bg-gray-100',
        iconClass: 'text-black',
      },
      {
        text: 'Desde su lanzamiento, ya han recibido reservas a través del sitio, y además ahora pueden llevar un control de sus reservaciones externas desde el mismo panel.',
        icon: TrendingUpIcon,
        iconBgClass: 'bg-gray-100',
        iconClass: 'text-black',
      },
    ],
    tags: [
      { text: 'WordPress', class: 'bg-gray-100 text-black' },
      { text: 'Sistema de Reservas', class: 'bg-gray-100 text-black' },
      { text: 'E-commerce', class: 'bg-gray-100 text-black' },
    ],
    stats: [
      { value: '100%', label: 'Reservas online', valueClass: 'text-black' },
      { value: '24/7', label: 'Disponibilidad', valueClass: 'text-black' },
    ],
  },
  {
    title: 'Tienda en línea para envío de flores y renta de mobiliario en Puebla',
    description:
      'Una empresa dedicada al envío de flores y renta de mobiliario para eventos en Puebla necesitaba una plataforma moderna que mostrara su catálogo de manera clara y permitiera gestionar pedidos fácilmente.',
    image: '/my-services/images/eventosa.png',
    imageAlt: 'Tienda de flores y mobiliario - E-commerce',
    features: [
      {
        text: 'Diseñé su tienda en Shopify con enfoque en usabilidad y visuales atractivos, organizando su catálogo de vajillas, loza, cristalería y mesas en colecciones fáciles de navegar.',
        icon: CheckSmallIcon,
        iconBgClass: 'bg-gray-100',
        iconClass: 'text-black',
      },
      {
        text: 'El nuevo sitio no solo ha facilitado la recepción de pedidos, también ha profesionalizado la presentación de sus productos para clientes que planean eventos desde casa o de forma corporativa.',
        icon: TrendingUpIcon,
        iconBgClass: 'bg-gray-100',
        iconClass: 'text-black',
      },
    ],
    tags: [
      { text: 'Shopify', class: 'bg-gray-100 text-black' },
      { text: 'E-commerce', class: 'bg-gray-100 text-black' },
      { text: 'Catálogo Digital', class: 'bg-gray-100 text-black' },
    ],
    stats: [
      { value: '+150%', label: 'Ventas online', valueClass: 'text-black' },
      { value: '24h', label: 'Entrega', valueClass: 'text-black' },
    ],
  },
  {
    title: 'Sitio web corporativo para restaurante tradicional mexicano',
    description:
      'Un restaurante con más de 20 años de tradición necesitaba modernizar su presencia digital para atraer a nuevos clientes y mostrar su auténtica cocina mexicana.',
    image: '/my-services/images/restaurante-mexicano.png',
    imageAlt: 'Restaurante mexicano - Sitio web corporativo',
    features: [
      {
        text: 'Creé un sitio web elegante y responsivo que destaca la historia del restaurante, su menú tradicional y la experiencia gastronómica única que ofrecen.',
        icon: CheckSmallIcon,
        iconBgClass: 'bg-gray-100',
        iconClass: 'text-black',
      },
      {
        text: 'El sitio incluye sistema de reservas online, galería de platillos, y está optimizado para búsquedas locales, aumentando significativamente las reservas.',
        icon: TrendingUpIcon,
        iconBgClass: 'bg-gray-100',
        iconClass: 'text-black',
      },
    ],
    tags: [
      { text: 'WordPress', class: 'bg-gray-100 text-black' },
      { text: 'Sistema de Reservas', class: 'bg-gray-100 text-black' },
      { text: 'SEO Local', class: 'bg-gray-100 text-black' },
    ],
    stats: [
      { value: '+80%', label: 'Reservas online', valueClass: 'text-black' },
      { value: '100%', label: 'Satisfacción', valueClass: 'text-black' },
    ],
  },
  {
    title: 'E-commerce para tienda de artesanías mexicanas',
    description:
      'Una emprendedora apasionada por las artesanías mexicanas necesitaba una plataforma que le permitiera vender sus productos a nivel nacional e internacional.',
    image: '/my-services/images/artesanias-mexicanas.png',
    imageAlt: 'Artesanías mexicanas - E-commerce',
    features: [
      {
        text: 'Desarrollé una tienda en línea completa con sistema de pagos internacionales, gestión de inventario y envíos a todo el mundo.',
        icon: CheckSmallIcon,
        iconBgClass: 'bg-gray-100',
        iconClass: 'text-black',
      },
      {
        text: 'El sitio incluye blog para contar historias de los artesanos, sistema de reseñas y está optimizado para conversiones, logrando ventas en 15 países.',
        icon: TrendingUpIcon,
        iconBgClass: 'bg-gray-100',
        iconClass: 'text-black',
      },
    ],
    tags: [
      { text: 'Shopify', class: 'bg-gray-100 text-black' },
      { text: 'E-commerce', class: 'bg-gray-100 text-black' },
      { text: 'Pagos Internacionales', class: 'bg-gray-100 text-black' },
    ],
    stats: [
      { value: '15+', label: 'Países', valueClass: 'text-black' },
      { value: '+200%', label: 'Ventas', valueClass: 'text-black' },
    ],
  },
])

defineExpose({
  successTitle,
  casesContainer,
  caseRefs,
})
</script>
