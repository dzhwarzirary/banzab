<template>
  <BrandProduct
    v-if="slugParts.length === 3"
    :brand-slug="slugParts[0]"
    :category-slug="slugParts[1]"
    :product-slug="slugParts[2]"
  />
  <BrandCategory
    v-else-if="slugParts.length === 2"
    :brand-slug="slugParts[0]"
    :category-slug="slugParts[1]"
  />
  <BrandDetail v-else-if="slugParts.length === 1" :brand-slug="slugParts[0]" />
  <div v-else class="pt-14 md:pt-16">
    <div class="max-w-6xl mx-auto px-6 md:px-8 py-20 text-center">
      <h1
        class="text-3xl md:text-4xl font-light text-gray-900 tracking-tight mb-5"
      >
        Page not found
      </h1>
      <p class="text-base text-gray-500 font-light mb-8">
        The page you're looking for doesn't exist or has been moved.
      </p>
      <NuxtLink
        to="/brands"
        class="inline-block bg-gray-900 text-white px-8 py-3.5 text-sm font-medium hover:bg-gray-800 transition-colors rounded-full"
      >
        Browse Brands
      </NuxtLink>
    </div>
  </div>
</template>

<script setup>
const route = useRoute();

const slugParts = computed(() => {
  if (Array.isArray(route.params.slug)) return route.params.slug;
  if (route.params.slug) return [route.params.slug];
  return [];
});
</script>
