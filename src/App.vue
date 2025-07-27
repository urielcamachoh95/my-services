<template>
  <div id="app" class="min-h-screen bg-background overflow-x-hidden">
    <!-- Navigation -->
    <SiteNavigation ref="navigation" />

    <!-- Hero Section -->
    <HeroSection ref="hero" />

    <!-- Client Logos Section -->
    <StatsSection ref="stats" />

    <!-- Why Work With Me Section -->
    <SectionContainer background-class="bg-gray-50" section-id="por-que-trabajar-conmigo">
      <WhyWorkWithMeSection ref="why" />
    </SectionContainer>

    <!-- Services Section -->
    <SectionContainer background-class="bg-white" section-id="servicios">
      <ServicesSection ref="services" />
    </SectionContainer>

    <!-- Success Cases Section -->
    <SectionContainer background-class="bg-gray-50">
      <SuccessCasesCarousel ref="successCases" />
    </SectionContainer>

    <!-- Testimonials Section -->
    <SectionContainer background-class="bg-white">
      <TestimonialsSection ref="testimonials" />
    </SectionContainer>

    <!-- Process Section -->
    <SectionContainer background-class="bg-gray-50" id="proceso">
      <ProcessSteps ref="process" />
    </SectionContainer>

    <!-- Contact Section -->
    <ContactSection ref="contact" id="contacto" />

    <!-- Footer -->
    <SiteFooter />
  </div>
</template>

<script setup lang="ts">
import { onMounted, ref, nextTick } from 'vue'
import { gsap } from 'gsap'
import { ScrollTrigger } from 'gsap/ScrollTrigger'

// Import components
import SiteNavigation from './components/SiteNavigation.vue'
import HeroSection from './components/HeroSection.vue'
import StatsSection from './components/StatsSection.vue'
import SectionContainer from './components/SectionContainer.vue'
import WhyWorkWithMeSection from './components/WhyWorkWithMeSection.vue'
import ServicesSection from './components/ServicesSection.vue'
import SuccessCasesCarousel from './components/SuccessCasesCarousel.vue'
import TestimonialsSection from './components/TestimonialsSection.vue'
import ProcessSteps from './components/ProcessSteps.vue'
import ContactSection from './components/ContactSection.vue'
import SiteFooter from './components/SiteFooter.vue'

// Register ScrollTrigger plugin
gsap.registerPlugin(ScrollTrigger)

// Component refs
const navigation = ref<InstanceType<typeof SiteNavigation>>()
const hero = ref<InstanceType<typeof HeroSection>>()
const stats = ref<InstanceType<typeof StatsSection>>()
const why = ref<InstanceType<typeof WhyWorkWithMeSection>>()
const services = ref<InstanceType<typeof ServicesSection>>()
const successCases = ref<InstanceType<typeof SuccessCasesCarousel>>()
const testimonials = ref<InstanceType<typeof TestimonialsSection>>()
const process = ref<InstanceType<typeof ProcessSteps>>()
const contact = ref<InstanceType<typeof ContactSection>>()

onMounted(async () => {
  // Wait for next tick to ensure all components are mounted
  await nextTick()

  // Add a small delay to ensure all components are fully rendered
  await new Promise((resolve) => setTimeout(resolve, 100))

  // Ensure all sections are visible immediately
  gsap.set('section', { opacity: 1, visibility: 'visible' })
  gsap.set('.section-padding', { opacity: 1, visibility: 'visible' })

  // Simple initial animations for hero only
  const tl = gsap.timeline()

  if (navigation.value?.logo) {
    tl.from(navigation.value.logo, {
      y: -50,
      opacity: 0,
      duration: 1,
      ease: 'power3.out',
    })
  }

  if (
    hero.value?.heroImage &&
    hero.value?.heroTitle &&
    hero.value?.heroSubtitle &&
    hero.value?.heroDescription &&
    hero.value?.heroButtons
  ) {
    tl.from(
      hero.value.heroImage,
      {
        scale: 0,
        opacity: 0,
        duration: 1,
        ease: 'back.out(1.7)',
      },
      '-=0.5',
    )
      .from(
        hero.value.heroTitle,
        {
          y: 100,
          opacity: 0,
          duration: 1,
          ease: 'power3.out',
        },
        '-=0.3',
      )
      .from(
        hero.value.heroSubtitle,
        {
          y: 50,
          opacity: 0,
          duration: 0.8,
          ease: 'power3.out',
        },
        '-=0.5',
      )
      .from(
        hero.value.heroDescription,
        {
          y: 50,
          opacity: 0,
          duration: 0.8,
          ease: 'power3.out',
        },
        '-=0.3',
      )
      .from(
        hero.value.heroButtons,
        {
          y: 50,
          opacity: 0,
          duration: 0.8,
          ease: 'power3.out',
        },
        '-=0.3',
      )
  }

  // Simple scroll animations for other sections
  setTimeout(() => {
    // Stats animation
    if (stats.value?.statRefs && stats.value.statRefs.length > 0) {
      gsap.from(stats.value.statRefs, {
        scrollTrigger: {
          trigger: stats.value.statRefs[0],
          start: 'top 80%',
        },
        y: 30,
        opacity: 0,
        duration: 0.6,
        stagger: 0.1,
      })
    }

    // Why section animations
    if (why.value?.whyTitle) {
      gsap.from(why.value.whyTitle, {
        scrollTrigger: {
          trigger: why.value.whyTitle,
          start: 'top 80%',
        },
        y: 30,
        opacity: 0,
        duration: 0.6,
      })
    }

    // Services animations
    if (services.value?.servicesTitle) {
      gsap.from(services.value.servicesTitle, {
        scrollTrigger: {
          trigger: services.value.servicesTitle,
          start: 'top 80%',
        },
        y: 30,
        opacity: 0,
        duration: 0.6,
      })
    }

    if (services.value?.serviceRefs && services.value.serviceRefs.length > 0) {
      gsap.from(services.value.serviceRefs, {
        scrollTrigger: {
          trigger: services.value.serviceRefs[0],
          start: 'top 80%',
        },
        y: 60,
        opacity: 0,
        duration: 0.8,
        stagger: 0.3,
        ease: 'power3.out',
      })
    }

    // Success cases animations
    if (successCases.value?.successTitle) {
      gsap.from(successCases.value.successTitle, {
        scrollTrigger: {
          trigger: successCases.value.successTitle,
          start: 'top 80%',
        },
        y: 30,
        opacity: 0,
        duration: 0.6,
      })
    }

    // Process animations
    if (process.value?.processTitle) {
      gsap.from(process.value.processTitle, {
        scrollTrigger: {
          trigger: process.value.processTitle,
          start: 'top 80%',
        },
        y: 30,
        opacity: 0,
        duration: 0.6,
      })
    }

    // Testimonials animations
    if (testimonials.value?.testimonialsTitle) {
      gsap.from(testimonials.value.testimonialsTitle, {
        scrollTrigger: {
          trigger: testimonials.value.testimonialsTitle,
          start: 'top 80%',
        },
        y: 30,
        opacity: 0,
        duration: 0.6,
      })
    }

    // Contact animations
    if (contact.value?.contactTitle) {
      gsap.from(contact.value.contactTitle, {
        scrollTrigger: {
          trigger: contact.value.contactTitle,
          start: 'top 80%',
        },
        y: 30,
        opacity: 0,
        duration: 0.6,
      })
    }
  }, 500)

  // Smooth scroll for navigation links
  const navLinks = document.querySelectorAll('a[href^="#"]')
  navLinks.forEach((link) => {
    link.addEventListener('click', (e) => {
      e.preventDefault()
      const target = document.querySelector(link.getAttribute('href') || '')
      if (target) {
        gsap.to(window, {
          duration: 1,
          scrollTo: { y: target, offsetY: 80 },
          ease: 'power3.inOut',
        })
      }
    })
  })
})
</script>
