<template>
  <!-- Site Navigation Component -->
  <nav
    class="bg-white/95 backdrop-blur-md shadow-sm border-b border-gray-100 sticky top-0 z-50 transition-all duration-300"
  >
    <div class="container-custom">
      <div class="flex justify-between items-center py-4">
        <!-- Logo/Name -->
        <div class="text-xl font-semibold text-black" ref="logo">{{ logoText }}</div>

        <!-- Center Navigation -->
        <div class="hidden md:flex space-x-8">
          <a
            v-for="item in menuItems"
            :key="item.href"
            :href="item.href"
            class="text-gray-600 hover:text-black transition-colors duration-300 nav-link text-sm font-medium"
            >{{ item.text }}</a
          >
        </div>

        <!-- Right side - Contact info and social links -->
        <div class="hidden md:flex items-center space-x-6">
          <!-- Email -->
          <div class="flex items-center space-x-2">
            <span class="text-sm text-gray-600">{{ email }}</span>
            <button
              class="text-xs bg-gray-100 hover:bg-gray-200 px-2 py-1 rounded transition-colors duration-200"
            >
              Copy
            </button>
            <button
              class="text-xs bg-gray-100 hover:bg-gray-200 px-2 py-1 rounded transition-colors duration-200"
            >
              CV
            </button>
          </div>

          <!-- Social Links -->
          <div class="flex items-center space-x-4">
            <a
              v-for="social in socialLinks"
              :key="social.name"
              :href="social.href"
              class="text-gray-600 hover:text-black transition-colors duration-300 text-sm"
            >
              {{ social.name }}
            </a>
          </div>
        </div>

        <!-- Mobile menu button -->
        <div class="md:hidden">
          <button class="text-gray-600 hover:text-black transition-colors">
            <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24">
              <path
                stroke-linecap="round"
                stroke-linejoin="round"
                stroke-width="2"
                d="M4 6h16M4 12h16M4 18h16"
              ></path>
            </svg>
          </button>
        </div>
      </div>
    </div>
  </nav>
</template>

<script setup lang="ts">
import { ref } from 'vue'

interface MenuItem {
  href: string
  text: string
}

interface SocialLink {
  name: string
  href: string
}

interface Props {
  logoText?: string
  menuItems?: MenuItem[]
  email?: string
  socialLinks?: SocialLink[]
}

withDefaults(defineProps<Props>(), {
  logoText: 'Uriel Camacho',
  menuItems: () => [
    { href: '#servicios', text: 'Servicios' },
    { href: '#proceso', text: 'Proceso' },
    { href: '#contacto', text: 'Contacto' },
  ],
  email: 'contacto@urielcamacho.com',
  socialLinks: () => [
    { name: 'LinkedIn', href: 'https://linkedin.com' },
    { name: 'GitHub', href: 'https://github.com' },
    { name: 'Instagram', href: 'https://instagram.com' },
  ],
})

const logo = ref<HTMLElement>()

defineExpose({
  logo,
})
</script>
