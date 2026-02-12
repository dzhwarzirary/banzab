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
              >Drinks</span
            >
            <span class="w-1 h-1 rounded-full bg-gray-300"></span>
            <span
              class="text-[11px] uppercase tracking-[0.15em] text-gray-400 font-medium"
              >Since 2019</span
            >
          </div>

          <h1
            class="text-4xl md:text-5xl lg:text-7xl font-light text-gray-900 tracking-tight leading-[1.05] mb-6"
          >
            Smoothie Season
          </h1>

          <p
            class="text-base md:text-lg text-gray-500 font-light leading-relaxed max-w-xl"
          >
            Kurdistan's leading smoothie and juice brand with 6 active branches
            across Erbil. A new flagship dine-in experience opening soon.
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
              <div class="text-sm text-gray-900 font-light">2019</div>
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
                Branches
              </div>
              <div class="text-sm text-gray-900 font-light">6 active</div>
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
            Fresh, real, and made for you
          </h2>
        </div>
        <div>
          <p class="text-base text-gray-500 font-light leading-relaxed mb-6">
            Smoothie Season was founded in 2019 with a simple idea: bring
            genuinely fresh, high-quality smoothies and juices to Erbil. No
            concentrates, no artificial flavors — just real ingredients blended
            fresh for every order.
          </p>
          <p class="text-base text-gray-500 font-light leading-relaxed">
            What started as a single location has grown into 6 branches across
            the city, with a new flagship dine-in experience on the way at Erbil
            Avenue. Every branch follows the same standard: quality ingredients,
            clean spaces, and drinks that taste as good as they look.
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
            Fresh Ingredients
          </h3>
          <p class="text-sm text-gray-500 font-light leading-relaxed">
            Every smoothie and juice is made with real, fresh ingredients — no
            concentrates, no artificial flavors.
          </p>
        </div>
        <div class="bg-white p-8 md:p-10 text-center">
          <div
            class="inline-flex items-center justify-center w-10 h-10 rounded-full border border-gray-200 mb-5"
          >
            <span class="text-sm font-light text-gray-900">02</span>
          </div>
          <h3 class="text-lg font-light text-gray-900 tracking-tight mb-2">
            Modern Experience
          </h3>
          <p class="text-sm text-gray-500 font-light leading-relaxed">
            Designed spaces that feel welcoming and contemporary, setting a new
            standard for F&B retail in the region.
          </p>
        </div>
        <div class="bg-white p-8 md:p-10 text-center">
          <div
            class="inline-flex items-center justify-center w-10 h-10 rounded-full border border-gray-200 mb-5"
          >
            <span class="text-sm font-light text-gray-900">03</span>
          </div>
          <h3 class="text-lg font-light text-gray-900 tracking-tight mb-2">
            Rapid Growth
          </h3>
          <p class="text-sm text-gray-500 font-light leading-relaxed">
            From one location to six in under five years, with a flagship
            dine-in experience on the way.
          </p>
        </div>
      </div>
    </div>

    <!-- Menu Section -->
    <div class="max-w-6xl mx-auto px-6 md:px-8 mb-20 md:mb-28">
      <div class="text-center mb-14 md:mb-20">
        <p
          class="text-xs uppercase tracking-[0.15em] text-gray-400 font-medium mb-5"
        >
          Menu
        </p>
        <h2
          class="text-3xl md:text-4xl lg:text-5xl font-light text-gray-900 tracking-tight leading-tight mb-5"
        >
          What we serve
        </h2>
        <p class="text-base text-gray-500 font-light max-w-lg mx-auto">
          From fresh smoothies to protein shakes, every drink is made to order
          with real ingredients.
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
              ${{ product.price.toFixed(2) }}
            </span>
          </div>
          <p class="text-sm text-gray-500 font-light leading-relaxed mb-5">
            {{ product.description }}
          </p>
          <!-- Ingredients -->
          <div class="flex flex-wrap gap-1.5 mb-5">
            <span
              v-for="ingredient in product.ingredients.slice(0, 4)"
              :key="ingredient"
              class="px-2.5 py-1 bg-gray-50 text-[11px] text-gray-500 font-medium rounded-full"
            >
              {{ ingredient }}
            </span>
            <span
              v-if="product.ingredients.length > 4"
              class="px-2.5 py-1 bg-gray-50 text-[11px] text-gray-400 font-medium rounded-full"
            >
              +{{ product.ingredients.length - 4 }}
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
          Visit Smoothie Season
        </h2>
        <p
          class="text-base text-gray-400 font-light leading-relaxed max-w-lg mx-auto mb-8"
        >
          Find us at 6 locations across Erbil. New flagship dine-in experience
          coming soon to Erbil Avenue.
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
  { id: "smoothies", name: "Smoothies" },
  { id: "protein-shakes", name: "Protein Shakes" },
  { id: "frappe", name: "Frappe" },
  { id: "hot-drinks", name: "Hot Drinks" },
  { id: "iced-drinks", name: "Iced Drinks" },
];

const allProducts = {
  smoothies: [
    {
      id: "tropical-mango",
      name: "Tropical Mango Smoothie",
      description:
        "A tropical escape with fresh mango, pineapple, and coconut water",
      price: 8.99,
      ingredients: [
        "Fresh Mango",
        "Pineapple",
        "Coconut Water",
        "Lime Juice",
        "Agave",
      ],
      nutrition: { calories: 210, protein: 3, sugar: 45 },
    },
    {
      id: "green-power",
      name: "Green Power Smoothie",
      description: "Nutrient-packed blend of spinach, kale, apple, and banana",
      price: 9.99,
      ingredients: [
        "Spinach",
        "Kale",
        "Green Apple",
        "Banana",
        "Ginger",
        "Lemon",
        "Coconut Water",
      ],
      nutrition: { calories: 185, protein: 5, sugar: 28 },
    },
    {
      id: "berry-antioxidant",
      name: "Berry Antioxidant Blast",
      description: "Mixed berries packed with antioxidants and Greek yogurt",
      price: 8.49,
      ingredients: [
        "Blueberries",
        "Strawberries",
        "Raspberries",
        "Greek Yogurt",
        "Honey",
        "Almond Milk",
      ],
      nutrition: { calories: 220, protein: 15, sugar: 30 },
    },
  ],
  "protein-shakes": [
    {
      id: "chocolate-protein",
      name: "Chocolate Peanut Butter Protein",
      description: "Rich chocolate and peanut butter with 25g of protein",
      price: 11.99,
      ingredients: [
        "Chocolate Whey Protein",
        "Peanut Butter",
        "Banana",
        "Oats",
        "Almond Milk",
        "Cacao",
      ],
      nutrition: { calories: 380, protein: 25, sugar: 18 },
    },
    {
      id: "vanilla-berry-protein",
      name: "Vanilla Berry Protein Shake",
      description:
        "Vanilla protein with fresh berries for post-workout recovery",
      price: 10.99,
      ingredients: [
        "Vanilla Whey Protein",
        "Mixed Berries",
        "Greek Yogurt",
        "Spinach",
        "Almond Milk",
      ],
      nutrition: { calories: 310, protein: 28, sugar: 20 },
    },
  ],
  frappe: [
    {
      id: "caramel-frappe",
      name: "Caramel Coffee Frappe",
      description:
        "Iced coffee blended with caramel and topped with whipped cream",
      price: 5.99,
      ingredients: [
        "Espresso",
        "Caramel Syrup",
        "Milk",
        "Ice",
        "Whipped Cream",
      ],
      nutrition: { calories: 290, protein: 6, sugar: 42 },
    },
    {
      id: "mocha-frappe",
      name: "Chocolate Mocha Frappe",
      description: "Rich chocolate and coffee blend with a hint of vanilla",
      price: 6.49,
      ingredients: [
        "Espresso",
        "Chocolate Syrup",
        "Milk",
        "Vanilla",
        "Ice",
        "Whipped Cream",
      ],
      nutrition: { calories: 320, protein: 8, sugar: 44 },
    },
  ],
  "hot-drinks": [
    {
      id: "golden-turmeric-latte",
      name: "Golden Turmeric Latte",
      description: "Warming turmeric and spice blend with steamed milk",
      price: 4.99,
      ingredients: [
        "Turmeric",
        "Ginger",
        "Cinnamon",
        "Black Pepper",
        "Coconut Milk",
        "Honey",
      ],
      nutrition: { calories: 150, protein: 3, sugar: 18 },
    },
    {
      id: "chai-tea-latte",
      name: "Spiced Chai Tea Latte",
      description: "Traditional chai spices with steamed milk and honey",
      price: 4.49,
      ingredients: [
        "Black Tea",
        "Cardamom",
        "Cinnamon",
        "Ginger",
        "Cloves",
        "Milk",
        "Honey",
      ],
      nutrition: { calories: 180, protein: 6, sugar: 26 },
    },
  ],
  "iced-drinks": [
    {
      id: "cucumber-mint-water",
      name: "Cucumber Mint Infused Water",
      description: "Refreshing cucumber and mint infused sparkling water",
      price: 3.99,
      ingredients: ["Cucumber", "Fresh Mint", "Sparkling Water", "Lime"],
      nutrition: { calories: 10, protein: 0, sugar: 2 },
    },
    {
      id: "hibiscus-iced-tea",
      name: "Hibiscus Iced Tea",
      description: "Tart and floral hibiscus tea served over ice with agave",
      price: 3.49,
      ingredients: ["Hibiscus Tea", "Agave", "Lemon", "Ice"],
      nutrition: { calories: 45, protein: 0, sugar: 11 },
    },
  ],
};

const activeCategory = ref("smoothies");

const activeProducts = computed(() => {
  return allProducts[activeCategory.value] || [];
});

useHead({
  title: "Smoothie Season - Banzab Portfolio",
  meta: [
    {
      name: "description",
      content:
        "Smoothie Season — Kurdistan's leading smoothie and juice brand with 6 branches across Erbil. Explore our full menu.",
    },
  ],
});
</script>
