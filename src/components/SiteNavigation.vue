<template>
  <nav
    class="fixed top-0 left-0 right-0 z-50 bg-white/90 backdrop-blur-md border-b border-slate-200/50"
  >
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      <div class="flex justify-between items-center h-16">
        <!-- Logo -->
        <div class="flex-shrink-0">
          <a href="#" class="text-xl font-bold text-slate-800">Uriel Camacho</a>
        </div>

        <!-- Desktop Navigation -->
        <div class="hidden md:flex items-center space-x-8">
          <a
            v-for="item in menuItems"
            :key="item.href"
            :href="item.href"
            class="text-slate-600 hover:text-cyan-600 transition-colors duration-300"
          >
            {{ item.text }}
          </a>
          <a href="#contacto" class="vapor-btn-primary text-sm">
            {{ ctaText }}
          </a>
        </div>

        <!-- Mobile menu button -->
        <div class="md:hidden">
          <button
            @click="toggleMobileMenu"
            class="text-slate-600 hover:text-cyan-600 transition-colors duration-300"
            :class="{ 'text-cyan-600': isMobileMenuOpen }"
          >
            <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24">
              <path
                v-if="!isMobileMenuOpen"
                stroke-linecap="round"
                stroke-linejoin="round"
                stroke-width="2"
                d="M4 6h16M4 12h16M4 18h16"
              />
              <path
                v-else
                stroke-linecap="round"
                stroke-linejoin="round"
                stroke-width="2"
                d="M6 18L18 6M6 6l12 12"
              />
            </svg>
          </button>
        </div>
      </div>

      <!-- Mobile Navigation Menu -->
      <div v-show="isMobileMenuOpen" class="md:hidden mobile-menu-transition" ref="mobileMenu">
        <div class="px-2 pt-2 pb-3 space-y-1 border-t border-slate-200/50">
          <a
            v-for="item in menuItems"
            :key="item.href"
            :href="item.href"
            @click="closeMobileMenu"
            class="block px-3 py-2 text-base font-medium text-slate-600 hover:text-cyan-600 hover:bg-cyan-50 rounded-md transition-colors duration-300"
          >
            {{ item.text }}
          </a>
          <a
            href="#contacto"
            @click="closeMobileMenu"
            class="block px-3 py-2 text-base font-medium text-cyan-600 hover:bg-cyan-50 rounded-md transition-colors duration-300"
          >
            {{ ctaText }}
          </a>
        </div>
      </div>
    </div>
  </nav>
</template>

<script setup lang="ts">
import { ref, onMounted, onUnmounted } from 'vue'

interface Props {
  menuItems?: Array<{ href: string; text: string }>
  ctaText?: string
}

withDefaults(defineProps<Props>(), {
  menuItems: () => [
    { href: '#servicios', text: 'Servicios' },
    { href: '#proceso', text: 'Proceso' },
    { href: '#faq', text: 'FAQ' },
    { href: '#contacto', text: 'Hablemos' },
  ],
  ctaText: 'Hablemos',
})

const isMobileMenuOpen = ref(false)
const mobileMenu = ref<HTMLElement>()

const toggleMobileMenu = () => {
  isMobileMenuOpen.value = !isMobileMenuOpen.value
}

const closeMobileMenu = () => {
  isMobileMenuOpen.value = false
}

// Close mobile menu on scroll
const handleScroll = () => {
  if (isMobileMenuOpen.value) {
    closeMobileMenu()
  }
}

onMounted(() => {
  window.addEventListener('scroll', handleScroll)
})

onUnmounted(() => {
  window.removeEventListener('scroll', handleScroll)
})
</script>
