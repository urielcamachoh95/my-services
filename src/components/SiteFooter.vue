<template>
  <footer class="py-8 bg-white border-t border-gray-100">
    <div class="container-custom">
      <div class="flex flex-col md:flex-row justify-between items-center">
        <!-- Copyright -->
        <div class="text-gray-600 text-sm mb-4 md:mb-0">
          © 2024 Uriel Camacho. Todos los derechos reservados.
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
    </div>
  </footer>
</template>

<script setup lang="ts">
interface SocialLink {
  name: string
  href: string
}

interface Props {
  socialLinks?: SocialLink[]
}

withDefaults(defineProps<Props>(), {
  socialLinks: () => [
    { name: 'LinkedIn', href: 'https://linkedin.com' },
    { name: 'GitHub', href: 'https://github.com' },
    { name: 'Instagram', href: 'https://instagram.com' },
  ],
})
</script>
