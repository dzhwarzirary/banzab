<template>
  <div class="pt-14 md:pt-16">
    <!-- Back Link + Header -->
    <div class="max-w-6xl mx-auto px-6 md:px-8 mb-16 md:mb-24">
      <NuxtLink
        to="/portfolio"
        class="inline-flex items-center gap-2 text-sm text-gray-400 font-light hover:text-gray-900 transition-colors mb-6"
      >
        <svg
          class="w-4 h-4"
          fill="none"
          stroke="currentColor"
          viewBox="0 0 24 24"
        >
          <path
            stroke-linecap="round"
            stroke-linejoin="round"
            stroke-width="1.5"
            d="M7 17l-4-4m0 0l4-4m-4 4h18"
          />
        </svg>
        <span>Portfolio</span>
      </NuxtLink>

      <div class="grid grid-cols-1 md:grid-cols-12 gap-10 md:gap-8 items-end">
        <!-- Left: Title + Description -->
        <div class="md:col-span-7">
          <div class="flex items-center gap-3 mb-5">
            <span
              class="text-[11px] uppercase tracking-[0.15em] text-gray-400 font-medium"
              >Snacks</span
            >
            <span class="w-1 h-1 rounded-full bg-gray-300"></span>
            <span
              class="text-[11px] uppercase tracking-[0.15em] text-gray-400 font-medium"
              >2025</span
            >
          </div>

          <h1
            class="text-4xl md:text-5xl lg:text-7xl font-light text-gray-900 tracking-tight leading-[1.05] mb-6"
          >
            Pyarra
          </h1>

          <p
            class="text-base md:text-lg text-gray-500 font-light leading-relaxed max-w-xl"
          >
            A line of healthy snacks built on quality and authenticity. Starting
            with protein bars and granolas, Pyarra brings better options to
            Kurdistan's snacking market.
          </p>
        </div>

        <!-- Right: Metadata -->
        <div class="md:col-span-5">
          <div class="grid grid-cols-2 gap-x-8 gap-y-6">
            <div>
              <div
                class="text-[11px] uppercase tracking-[0.12em] text-gray-400 font-medium mb-1.5"
              >
                Sector
              </div>
              <div class="text-sm text-gray-900 font-light">
                Food & Beverage
              </div>
            </div>
            <div>
              <div
                class="text-[11px] uppercase tracking-[0.12em] text-gray-400 font-medium mb-1.5"
              >
                Founded
              </div>
              <div class="text-sm text-gray-900 font-light">2025</div>
            </div>
            <div>
              <div
                class="text-[11px] uppercase tracking-[0.12em] text-gray-400 font-medium mb-1.5"
              >
                Location
              </div>
              <div class="text-sm text-gray-900 font-light">
                Erbil, Kurdistan
              </div>
            </div>
            <div>
              <div
                class="text-[11px] uppercase tracking-[0.12em] text-gray-400 font-medium mb-1.5"
              >
                Category
              </div>
              <div class="text-sm text-gray-900 font-light">Healthy snacks</div>
            </div>
          </div>
        </div>
      </div>
    </div>

    <!-- About -->
    <div class="max-w-6xl mx-auto px-6 md:px-8 mb-20 md:mb-28">
      <div class="grid grid-cols-1 md:grid-cols-2 gap-12 md:gap-16">
        <div>
          <p
            class="text-xs uppercase tracking-[0.15em] text-gray-400 font-medium mb-5"
          >
            About
          </p>
          <h2
            class="text-3xl md:text-4xl font-light text-gray-900 tracking-tight leading-tight"
          >
            Snacks that set a higher standard
          </h2>
        </div>
        <div>
          <p class="text-base text-gray-500 font-light leading-relaxed mb-6">
            Pyarra was born out of a simple frustration: the lack of genuinely
            healthy, high-quality snack options in Kurdistan. We set out to
            change that with products that are honest about what's inside — real
            ingredients, high protein, and no unnecessary additives.
          </p>
          <p class="text-base text-gray-500 font-light leading-relaxed">
            Launching with protein bars and granolas, Pyarra is just getting
            started. Every product is developed with nutrition in mind, designed
            to fuel your day without compromising on taste or quality.
          </p>
        </div>
      </div>
    </div>

    <!-- Highlights -->
    <div class="max-w-6xl mx-auto px-6 md:px-8 mb-20 md:mb-28">
      <div
        class="grid grid-cols-1 md:grid-cols-3 gap-px bg-gray-200 rounded-2xl overflow-hidden"
      >
        <div class="bg-white p-8 md:p-10 text-center">
          <div
            class="inline-flex items-center justify-center w-10 h-10 rounded-full border border-gray-200 mb-5"
          >
            <span class="text-sm font-light text-gray-900">01</span>
          </div>
          <h3 class="text-lg font-light text-gray-900 tracking-tight mb-2">
            Health-First
          </h3>
          <p class="text-sm text-gray-500 font-light leading-relaxed">
            Every product is designed with nutrition in mind — high protein,
            natural ingredients, no unnecessary additives.
          </p>
        </div>
        <div class="bg-white p-8 md:p-10 text-center">
          <div
            class="inline-flex items-center justify-center w-10 h-10 rounded-full border border-gray-200 mb-5"
          >
            <span class="text-sm font-light text-gray-900">02</span>
          </div>
          <h3 class="text-lg font-light text-gray-900 tracking-tight mb-2">
            Local Market Gap
          </h3>
          <p class="text-sm text-gray-500 font-light leading-relaxed">
            Filling a genuine need for quality, healthy snack options that
            didn't previously exist in Kurdistan.
          </p>
        </div>
        <div class="bg-white p-8 md:p-10 text-center">
          <div
            class="inline-flex items-center justify-center w-10 h-10 rounded-full border border-gray-200 mb-5"
          >
            <span class="text-sm font-light text-gray-900">03</span>
          </div>
          <h3 class="text-lg font-light text-gray-900 tracking-tight mb-2">
            Growing Range
          </h3>
          <p class="text-sm text-gray-500 font-light leading-relaxed">
            Launching with protein bars and granolas, with plans to expand into
            a full range of healthy snack products.
          </p>
        </div>
      </div>
    </div>

    <!-- Products Section -->
    <div class="max-w-6xl mx-auto px-6 md:px-8 mb-20 md:mb-28">
      <div class="text-center mb-14 md:mb-20">
        <p
          class="text-xs uppercase tracking-[0.15em] text-gray-400 font-medium mb-5"
        >
          Products
        </p>
        <h2
          class="text-3xl md:text-4xl lg:text-5xl font-light text-gray-900 tracking-tight leading-tight mb-5"
        >
          Our range
        </h2>
        <p class="text-base text-gray-500 font-light max-w-lg mx-auto">
          High-protein, real-ingredient snacks designed to fuel your day.
        </p>
      </div>

      <!-- Category Tabs -->
      <div class="flex flex-wrap justify-center gap-2 mb-12 md:mb-16">
        <button
          v-for="category in categories"
          :key="category.id"
          @click="activeCategory = category.id"
          :class="[
            'px-5 py-2.5 rounded-full text-sm font-medium transition-all',
            activeCategory === category.id
              ? 'bg-gray-900 text-white'
              : 'bg-gray-100 text-gray-500 hover:bg-gray-200 hover:text-gray-700',
          ]"
        >
          {{ category.name }}
        </button>
      </div>

      <!-- Products Grid -->
      <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-5">
        <div
          v-for="product in activeProducts"
          :key="product.id"
          class="rounded-2xl border border-gray-100 p-6"
        >
          <div class="flex items-start justify-between mb-4">
            <h3
              class="text-lg font-light text-gray-900 tracking-tight leading-snug pr-4"
            >
              {{ product.name }}
            </h3>
            <span class="text-sm font-light text-gray-400 flex-shrink-0">
              {{ product.weight }}
            </span>
          </div>
          <p class="text-sm text-gray-500 font-light leading-relaxed mb-5">
            {{ product.description }}
          </p>
          <!-- Key Ingredients -->
          <div class="flex flex-wrap gap-1.5 mb-5">
            <span
              v-for="ingredient in product.highlights"
              :key="ingredient"
              class="px-2.5 py-1 bg-gray-50 text-[11px] text-gray-500 font-medium rounded-full"
            >
              {{ ingredient }}
            </span>
          </div>
          <!-- Nutrition -->
          <div class="flex items-center gap-5 pt-5 border-t border-gray-100">
            <div>
              <div class="text-sm font-light text-gray-900">
                {{ product.nutrition.calories }}
              </div>
              <div class="text-[10px] uppercase tracking-[0.1em] text-gray-400">
                Cal
              </div>
            </div>
            <div>
              <div class="text-sm font-light text-gray-900">
                {{ product.nutrition.protein }}g
              </div>
              <div class="text-[10px] uppercase tracking-[0.1em] text-gray-400">
                Protein
              </div>
            </div>
            <div>
              <div class="text-sm font-light text-gray-900">
                {{ product.nutrition.fiber }}g
              </div>
              <div class="text-[10px] uppercase tracking-[0.1em] text-gray-400">
                Fiber
              </div>
            </div>
            <div>
              <div class="text-sm font-light text-gray-900">
                {{ product.nutrition.sugar }}g
              </div>
              <div class="text-[10px] uppercase tracking-[0.1em] text-gray-400">
                Sugar
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>

    <!-- CTA -->
    <div class="max-w-6xl mx-auto px-6 md:px-8 mb-16 md:mb-20">
      <div class="bg-gray-950 rounded-3xl p-10 md:p-14 lg:p-20 text-center">
        <h2
          class="text-3xl md:text-4xl font-light text-white tracking-tight mb-5 leading-tight"
        >
          Try Pyarra
        </h2>
        <p
          class="text-base text-gray-400 font-light leading-relaxed max-w-lg mx-auto mb-8"
        >
          Available now across Erbil. Interested in stocking Pyarra or
          partnership opportunities?
        </p>
        <NuxtLink
          to="/contact"
          class="inline-flex items-center gap-3 text-white border border-white/30 px-8 py-3.5 rounded-full text-sm font-medium hover:bg-white/10 hover:border-white/50 transition-all"
        >
          <span>Get in Touch</span>
          <svg
            class="w-4 h-4"
            fill="none"
            stroke="currentColor"
            viewBox="0 0 24 24"
          >
            <path
              stroke-linecap="round"
              stroke-linejoin="round"
              stroke-width="1.5"
              d="M17 8l4 4m0 0l-4 4m4-4H3"
            />
          </svg>
        </NuxtLink>
      </div>
    </div>
  </div>
</template>

<script setup>
const categories = [
  { id: "protein-bars", name: "Protein Bars" },
  { id: "granola", name: "Granola" },
  { id: "energy-bites", name: "Energy Bites" },
];

const products = {
  "protein-bars": [
    {
      id: "chocolate-almond",
      name: "Chocolate Almond Crunch",
      description:
        "Dark chocolate with roasted almonds and a hint of sea salt. 20g protein per bar.",
      weight: "60g",
      highlights: ["Dark Chocolate", "Almonds", "Whey Protein", "Sea Salt"],
      nutrition: { calories: 230, protein: 20, fiber: 4, sugar: 6 },
    },
    {
      id: "peanut-butter",
      name: "Peanut Butter Power",
      description:
        "Creamy peanut butter core with oats and honey. A satisfying post-workout treat.",
      weight: "60g",
      highlights: ["Peanut Butter", "Oats", "Honey", "Whey Protein"],
      nutrition: { calories: 250, protein: 22, fiber: 3, sugar: 8 },
    },
    {
      id: "coconut-cashew",
      name: "Coconut Cashew",
      description:
        "Toasted coconut and cashews with vanilla whey. Light, crunchy, and clean.",
      weight: "55g",
      highlights: ["Coconut", "Cashews", "Vanilla", "Whey Protein"],
      nutrition: { calories: 210, protein: 18, fiber: 3, sugar: 5 },
    },
  ],
  granola: [
    {
      id: "honey-oat",
      name: "Honey Oat Classic",
      description:
        "Slow-baked oats with raw honey, toasted almonds, and golden raisins.",
      weight: "350g",
      highlights: ["Rolled Oats", "Raw Honey", "Almonds", "Raisins"],
      nutrition: { calories: 180, protein: 6, fiber: 5, sugar: 9 },
    },
    {
      id: "dark-chocolate-cherry",
      name: "Dark Chocolate & Cherry",
      description:
        "Rich cacao nibs with dried cherries and a touch of cinnamon. Indulgent but balanced.",
      weight: "350g",
      highlights: ["Cacao Nibs", "Dried Cherries", "Cinnamon", "Oats"],
      nutrition: { calories: 195, protein: 5, fiber: 4, sugar: 11 },
    },
    {
      id: "tropical-crunch",
      name: "Tropical Crunch",
      description:
        "Mango, pineapple, and macadamia nuts with coconut flakes. A sunny morning in a bowl.",
      weight: "350g",
      highlights: ["Mango", "Pineapple", "Macadamia", "Coconut"],
      nutrition: { calories: 200, protein: 4, fiber: 3, sugar: 12 },
    },
  ],
  "energy-bites": [
    {
      id: "date-walnut",
      name: "Date & Walnut",
      description:
        "Medjool dates and walnuts rolled with cacao and a pinch of Himalayan salt.",
      weight: "8 pack",
      highlights: ["Medjool Dates", "Walnuts", "Cacao", "Pink Salt"],
      nutrition: { calories: 95, protein: 3, fiber: 2, sugar: 10 },
    },
    {
      id: "pistachio-lemon",
      name: "Pistachio & Lemon",
      description:
        "Bright lemon zest with crushed pistachios and oats. Fresh and energizing.",
      weight: "8 pack",
      highlights: ["Pistachios", "Lemon Zest", "Oats", "Honey"],
      nutrition: { calories: 85, protein: 4, fiber: 2, sugar: 7 },
    },
    {
      id: "almond-butter-banana",
      name: "Almond Butter & Banana",
      description:
        "Creamy almond butter with freeze-dried banana and chia seeds.",
      weight: "8 pack",
      highlights: ["Almond Butter", "Banana", "Chia Seeds", "Oats"],
      nutrition: { calories: 100, protein: 4, fiber: 3, sugar: 8 },
    },
  ],
};

const activeCategory = ref("protein-bars");

const activeProducts = computed(() => {
  return products[activeCategory.value] || [];
});

useHead({
  title: "Pyarra - Banzab Portfolio",
  meta: [
    {
      name: "description",
      content:
        "Pyarra — healthy snacks built on quality and authenticity. Protein bars, granolas, and energy bites made in Kurdistan.",
    },
  ],
});
</script>
