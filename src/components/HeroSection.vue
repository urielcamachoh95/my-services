<template>
  <section
    class="relative py-20 md:py-40 flex items-center justify-center bg-background overflow-hidden"
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

    <div class="container-custom px-4 sm:px-6 lg:px-8 relative z-10">
      <div class="max-w-4xl mx-auto text-center">
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
        <div class="flex flex-col sm:flex-row sm:justify-center gap-4" ref="heroButtons">
          <a
            href="https://wa.me/+5212212287141?text=Hola%20Uriel,%20me%20interesa%20trabajar%20contigo%20en%20mi%20negocio"
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
