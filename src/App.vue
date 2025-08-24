<template>
  <div id="app" class="min-h-screen bg-white overflow-x-hidden">
    <!-- Navigation -->
    <SiteNavigation ref="navigation" />

    <!-- Hero Section -->
    <section class="vapor-section-hero">
      <HeroSection ref="hero" />
    </section>

    <!-- Why Work With Me Section -->
    <section class="vapor-section-trust" id="por-que-trabajar-conmigo">
      <WhyWorkWithMeSection ref="why" />
    </section>

    <!-- Services Section -->
    <section class="vapor-section-services" id="servicios">
      <ServicesSection ref="services" />
    </section>

    <!-- Process Section -->
    <section class="vapor-section-process" id="proceso">
      <ProcessSteps ref="process" />
    </section>

    <!-- Success Cases Section -->
    <section class="vapor-section-proof">
      <div class="vapor-section-content">
        <SuccessCasesCarousel ref="successCases" />
      </div>
    </section>

    <!-- Testimonials Section -->
    <section class="vapor-section-proof">
      <div class="vapor-section-content">
        <TestimonialsSection ref="testimonials" />
      </div>
    </section>

    <!-- Stats Section -->
    <section class="vapor-section-stats" id="estadisticas">
      <StatsSection ref="stats" />
    </section>

    <!-- FAQ Section -->
    <section class="vapor-section-faq" id="faq">
      <FAQSection ref="faq" />
    </section>

    <!-- Contact Section -->
    <ContactSection ref="contact" id="contacto" />

    <!-- Footer -->
    <SiteFooter />
  </div>
</template>

<script setup lang="ts">
import { onMounted } from 'vue'

// Import components
import SiteNavigation from './components/SiteNavigation.vue'
import HeroSection from './components/HeroSection.vue'
import StatsSection from './components/StatsSection.vue'
import WhyWorkWithMeSection from './components/WhyWorkWithMeSection.vue'
import ServicesSection from './components/ServicesSection.vue'
import SuccessCasesCarousel from './components/SuccessCasesCarousel.vue'
import TestimonialsSection from './components/TestimonialsSection.vue'
import ProcessSteps from './components/ProcessSteps.vue'
import FAQSection from './components/FAQSection.vue'
import ContactSection from './components/ContactSection.vue'
import SiteFooter from './components/SiteFooter.vue'

// Simple scroll observer for fade-in animations
onMounted(() => {
  const observerOptions = {
    threshold: 0.1,
    rootMargin: '0px 0px -50px 0px',
  }

  const observer = new IntersectionObserver((entries) => {
    entries.forEach((entry) => {
      if (entry.isIntersecting) {
        entry.target.classList.add('visible')
      }
    })
  }, observerOptions)

  // Observe all fade-in elements
  const fadeElements = document.querySelectorAll('.vapor-fade-in')
  fadeElements.forEach((el) => observer.observe(el))

  // Simple smooth scroll for navigation links
  const navLinks = document.querySelectorAll('a[href^="#"]')
  navLinks.forEach((link) => {
    link.addEventListener('click', (e) => {
      e.preventDefault()
      const target = document.querySelector(link.getAttribute('href') || '')
      if (target) {
        target.scrollIntoView({ behavior: 'smooth', block: 'start' })
      }
    })
  })
})
</script>
