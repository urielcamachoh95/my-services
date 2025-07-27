<template>
  <section
    class="relative min-h-screen flex items-center justify-center bg-background overflow-hidden py-20"
  >
    <!-- Background Image -->
    <div class="absolute inset-0 z-0">
      <img
        src="https://images.unsplash.com/photo-1451187580459-43490279c0fa?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=2000&q=80"
        alt="Background"
        class="w-full h-full object-cover opacity-10"
      />
      <div
        class="absolute inset-0 bg-gradient-to-b from-transparent via-background/50 to-background"
      ></div>
    </div>

    <div class="container-custom relative z-10">
      <div class="max-w-4xl mx-auto text-center">
        <!-- Profile Image with bubble -->
        <div class="mb-12 flex justify-center" ref="heroImage">
          <div class="relative">
            <img
              :src="profileImage"
              :alt="profileAlt"
              class="w-24 h-24 rounded-full mx-auto object-cover shadow-lg border-4 border-white"
            />
            <!-- Name bubble -->
            <div
              class="absolute -bottom-2 -right-2 bg-white rounded-full px-3 py-1 shadow-sm border border-gray-100"
            >
              <span class="text-sm font-medium text-gray-800">{{ name }}</span>
            </div>
          </div>
        </div>

        <!-- Main Headline -->
        <h1 class="text-4xl md:text-6xl font-bold text-black mb-8 leading-tight" ref="heroTitle">
          <span class="text-black">
            {{ titleHighlight }}
          </span>
          <br />
          <span class="text-black/90">{{ titleSubtext }}</span>
        </h1>

        <!-- Subtitle -->
        <p
          class="text-xl md:text-2xl text-gray-600 mb-8 leading-relaxed max-w-4xl mx-auto"
          ref="heroSubtitle"
        >
          {{ subtitle }}
        </p>

        <!-- Description -->
        <p
          class="text-lg text-gray-600 mb-12 leading-relaxed max-w-3xl mx-auto"
          ref="heroDescription"
        >
          {{ description }}
        </p>

        <!-- Call to Action Buttons -->
        <div class="flex flex-col sm:flex-row gap-6 justify-center items-center" ref="heroButtons">
          <a :href="primaryButton.href" class="btn-primary text-lg group">
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
                d="M17 8l4 4m0 0l-4 4m4-4H3"
              ></path>
            </svg>
          </a>
          <a
            href="#servicios"
            class="btn-secondary text-lg group"
            @click.prevent="scrollToServices"
          >
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
                d="M19 9l-7 7-7-7"
              ></path>
            </svg>
          </a>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
import { ref } from 'vue'
import { gsap } from 'gsap'
import { ScrollToPlugin } from 'gsap/ScrollToPlugin'

// Register the ScrollToPlugin
gsap.registerPlugin(ScrollToPlugin)

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
  titleHighlight: 'Páginas web y sistemas',
  titleSubtext: 'que hacen crecer tu negocio',
  subtitle:
    'Hola, soy Uriel Camacho, desarrollador web. Trabajo con pequeñas y medianas empresas que quieren vender en línea, automatizar procesos o mejorar su presencia en Internet.',
  description:
    'Me encargo de entender a fondo tu negocio con un enfoque claro: ayudarte a avanzar con lo que realmente necesitas.',
  primaryButton: () => ({ text: 'Hablemos de tu negocio', href: '#contacto' }),
  secondaryButton: () => ({ text: 'Ver servicios', href: '#servicios' }),
})

const heroImage = ref<HTMLElement>()
const heroTitle = ref<HTMLElement>()
const heroSubtitle = ref<HTMLElement>()
const heroDescription = ref<HTMLElement>()
const heroButtons = ref<HTMLElement>()

// Function to scroll to services section
const scrollToServices = () => {
  const servicesSection = document.querySelector('#servicios') as HTMLElement
  if (servicesSection) {
    gsap.to(window, {
      duration: 1,
      scrollTo: {
        y: servicesSection,
        offsetY: 100,
      },
      ease: 'power2.inOut',
    })
  }
}

defineExpose({
  heroImage,
  heroTitle,
  heroSubtitle,
  heroDescription,
  heroButtons,
})
</script>
