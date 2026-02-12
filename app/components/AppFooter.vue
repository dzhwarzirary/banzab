<template>
  <footer class="bg-gray-950 text-white">
    <div class="max-w-6xl mx-auto px-6 md:px-8">
      <!-- Main Footer -->
      <div class="py-16 md:py-20">
        <div class="grid grid-cols-1 md:grid-cols-12 gap-12 md:gap-8">
          <!-- Brand -->
          <div class="md:col-span-5">
            <NuxtLink
              to="/"
              class="text-2xl font-medium text-white tracking-tight"
            >
              Banzab
            </NuxtLink>
            <p
              class="text-sm text-gray-400 font-light leading-relaxed mt-4 max-w-sm"
            >
              Building exceptional companies that bring quality, innovation, and
              higher standards to Kurdistan's food and beverage market.
            </p>
          </div>

          <!-- Navigation -->
          <div class="md:col-span-3">
            <p
              class="text-[11px] uppercase tracking-[0.15em] text-gray-500 font-medium mb-5"
            >
              Navigate
            </p>
            <ul class="space-y-3">
              <li v-for="link in navLinks" :key="link.name">
                <NuxtLink
                  :to="link.href"
                  class="text-sm text-gray-400 font-light hover:text-white transition-colors"
                >
                  {{ link.name }}
                </NuxtLink>
              </li>
            </ul>
          </div>

          <!-- Contact -->
          <div class="md:col-span-4">
            <p
              class="text-[11px] uppercase tracking-[0.15em] text-gray-500 font-medium mb-5"
            >
              Contact
            </p>
            <div class="space-y-3">
              <p class="text-sm text-gray-400 font-light">
                Erbil, Kurdistan Region
              </p>
              <a
                href="mailto:hello@banzab.com"
                class="block text-sm text-gray-400 font-light hover:text-white transition-colors"
              >
                hello@banzab.com
              </a>
            </div>

            <!-- Social -->
            <div class="flex items-center gap-5 mt-6">
              <a
                v-for="social in socialLinks"
                :key="social.name"
                :href="social.href"
                class="text-xs uppercase tracking-[0.12em] text-gray-500 font-medium hover:text-white transition-colors"
              >
                {{ social.name }}
              </a>
            </div>
          </div>
        </div>
      </div>

      <!-- Bottom Bar -->
      <div
        class="border-t border-gray-800 py-6 flex flex-col md:flex-row justify-between items-center gap-3"
      >
        <p class="text-xs text-gray-500 font-light">
          &copy; {{ currentYear }} Banzab. All rights reserved.
        </p>
        <NuxtLink
          to="/privacy"
          class="text-xs text-gray-500 font-light hover:text-gray-300 transition-colors"
        >
          Privacy Policy
        </NuxtLink>
      </div>
    </div>
  </footer>
</template>

<script setup>
const currentYear = new Date().getFullYear();

const navLinks = [
  { name: "Portfolio", href: "/portfolio" },
  { name: "Newsroom", href: "/newsroom" },
  { name: "Our Story", href: "/about" },
  { name: "Contact", href: "/contact" },
];

const socialLinks = [
  { name: "Instagram", href: "#" },
  { name: "LinkedIn", href: "#" },
];
</script>
