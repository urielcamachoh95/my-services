<template>
  <footer class="relative py-12 overflow-hidden glass-section">
    <!-- Background with glassmorphism effect -->
    <div class="absolute inset-0 glass-bg-accent"></div>
    <div class="absolute inset-0 opacity-10">
      <div class="absolute inset-0 isometric-grid"></div>
    </div>

    <!-- Floating geometric shapes -->
    <div
      class="absolute top-8 right-8 w-16 h-16 bg-slate-100/40 rounded-xl transform rotate-12 animate-blob"
    ></div>
    <div
      class="absolute bottom-8 left-8 w-12 h-12 bg-slate-100/40 rounded-xl transform -rotate-12 animate-blob animation-delay-2000"
    ></div>

    <div class="container-custom relative z-10">
      <div class="flex flex-col md:flex-row justify-between items-center">
        <!-- Enhanced Copyright -->
        <div class="text-slate-600 text-sm mb-6 md:mb-0 group">
          <span
            class="bg-gradient-to-r from-cyan-600 to-sky-600 bg-clip-text text-transparent font-medium"
          >
            © {{ new Date().getFullYear() }} Uriel Camacho.
          </span>
          <span class="ml-1">Todos los derechos reservados.</span>
        </div>

        <!-- Enhanced Social Links -->
        <div class="flex items-center space-x-6">
          <a
            v-for="social in socialLinks"
            :key="social.name"
            :href="social.href"
            class="text-gray-500 hover:text-cyan-600 transition-all duration-300 text-sm flex items-center p-2 rounded-lg hover:bg-cyan-50 group"
            :title="social.name"
          >
            <svg
              v-if="social.name === 'LinkedIn'"
              class="w-5 h-5 group-hover:scale-110 transition-transform duration-300"
              fill="currentColor"
              viewBox="0 0 24 24"
            >
              <path
                d="M20.447 20.452h-3.554v-5.569c0-1.328-.027-3.037-1.852-3.037-1.853 0-2.136 1.445-2.136 2.939v5.667H9.351V9h3.414v1.561h.046c.477-.9 1.637-1.85 3.37-1.85 3.601 0 4.267 2.37 4.267 5.455v6.286zM5.337 7.433c-1.144 0-2.063-.926-2.063-2.065 0-1.138.92-2.063 2.063-2.063 1.14 0 2.064.925 2.064 2.063 0 1.139-.925 2.065-2.064 2.065zm1.782 13.019H3.555V9h3.564v11.452zM22.225 0H1.771C.792 0 0 .774 0 1.729v20.542C0 23.227.792 24 1.771 24h20.451C23.2 24 24 23.227 24 22.271V1.729C24 .774 23.2 0 22.222 0h.003z"
              />
            </svg>
            <svg
              v-else-if="social.name === 'GitHub'"
              class="w-5 h-5 group-hover:scale-110 transition-transform duration-300"
              fill="currentColor"
              viewBox="0 0 24 24"
            >
              <path
                d="M12 0c-6.626 0-12 5.373-12 12 0 5.302 3.438 9.8 8.207 11.387.599.111.793-.261.793-.577v-2.234c-3.338.726-4.033-1.416-4.033-1.416-.546-1.387-1.333-1.756-1.333-1.756-1.089-.745.083-.729.083-.729 1.205.084 1.839 1.237 1.839 1.237 1.07 1.834 2.807 1.304 3.492.997.107-.775.418-1.305.762-1.604-2.665-.305-5.467-1.334-5.467-5.931 0-1.311.469-2.381 1.236-3.221-.124-.303-.535-1.524.117-3.176 0 0 1.008-.322 3.301 1.23.957-.266 1.983-.399 3.003-.404 1.02.005 2.047.138 3.006.404 2.291-1.552 3.297-1.23 3.297-1.23.653 1.653.242 2.874.118 3.176.77.84 1.235 1.911 1.235 3.221 0 4.609-2.807 5.624-5.479 5.921.43.372.823 1.102.823 2.222v3.293c0 .319.192.694.801.576 4.765-1.589 8.199-6.086 8.199-11.386 0-6.627-5.373-12-12-12z"
              />
            </svg>
            <svg
              v-else-if="social.name === 'Instagram'"
              class="w-5 h-5 group-hover:scale-110 transition-transform duration-300"
              fill="currentColor"
              viewBox="0 0 24 24"
            >
              <path
                d="M12.017 0C5.396 0 .029 5.367.029 11.987c0 6.62 5.367 11.987 11.988 11.987 6.62 0 11.987-5.367 11.987-11.987C24.014 5.367 18.637.001 12.017.001zM8.449 16.988c-1.297 0-2.448-.49-3.323-1.297C4.198 14.895 3.708 13.744 3.708 12.447s.49-2.448 1.297-3.323c.875-.807 2.026-1.297 3.323-1.297s2.448.49 3.323 1.297c.807.875 1.297 2.026 1.297 3.323s-.49 2.448-1.297 3.323c-.875.807-2.026 1.297-3.323 1.297zm7.718-1.297c-.49.49-1.297.807-2.026.807s-1.536-.317-2.026-.807c-.49-.49-.807-1.297-.807-2.026s.317-1.536.807-2.026c.49-.49 1.297-.807 2.026-.807s1.536.317 2.026.807c.49.49.807 1.297.807 2.026s-.317 1.536-.807 2.026z"
              />
            </svg>
            <svg
              v-else-if="social.name === 'WhatsApp'"
              class="w-5 h-5 group-hover:scale-110 transition-transform duration-300"
              fill="currentColor"
              viewBox="0 0 24 24"
            >
              <path
                d="M17.472 14.382c-.297-.149-1.758-.867-2.03-.967-.273-.099-.471-.148-.67.15-.197.297-.767.966-.94 1.164-.173.199-.347.223-.644.075-.297-.15-1.255-.463-2.39-1.475-.883-.788-1.48-1.761-1.653-2.059-.173-.297-.018-.458.13-.606.134-.133.298-.347.446-.52.149-.174.198-.298.298-.497.099-.198.05-.371-.025-.52-.075-.149-.669-1.612-.916-2.207-.242-.579-.487-.5-.669-.51-.173-.008-.371-.01-.57-.01-.198 0-.52.074-.792.372-.272.297-1.04 1.016-1.04 2.479 0 1.462 1.065 2.875 1.213 3.074.149.198 2.096 3.2 5.077 4.487.709.306 1.262.489 1.694.625.712.227 1.36.195 1.871.118.571-.085 1.758-.719 2.006-1.413.248-.694.248-1.289.173-1.413-.074-.124-.272-.198-.57-.347m-5.421 7.403h-.004a9.87 9.87 0 01-5.031-1.378l-.361-.214-3.741.982.998-3.648-.235-.374a9.86 9.86 0 01-1.51-5.26c.001-5.45 4.436-9.884 9.888-9.884 2.64 0 5.122 1.03 6.988 2.898a9.825 9.825 0 012.893 6.994c-.003 5.45-4.437 9.884-9.885 9.884m8.413-18.297A11.815 11.815 0 0012.05 0C5.495 0 .16 5.335.157 11.892c0 2.096.547 4.142 1.588 5.945L.057 24l6.305-1.654a11.882 11.882 0 005.683 1.448h.005c6.554 0 11.89-5.335 11.893-11.893A11.821 11.821 0 0020.885 3.488"
              />
            </svg>
            <span v-else>{{ social.name }}</span>
          </a>
        </div>
      </div>

      <!-- Additional footer content -->
      <div class="mt-8 pt-8 border-t border-gray-200 text-center">
        <p class="text-xs text-gray-500">
          Desarrollado con atención al detalle para emprendedores que quieren crecer
        </p>
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
    { name: 'WhatsApp', href: 'https://wa.me/+5212212287141' },
    { name: 'LinkedIn', href: 'https://www.linkedin.com/in/uriel-camacho' },
    { name: 'GitHub', href: 'https://github.com/urielcamachoh95' },
    { name: 'Instagram', href: 'https://www.instagram.com/ucamacho95' },
  ],
})
</script>
