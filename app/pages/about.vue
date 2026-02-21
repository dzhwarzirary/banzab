<template>
  <div class="pt-14 md:pt-16">
    <!-- Centered Header -->
    <div class="max-w-3xl mx-auto px-6 md:px-8 text-center mb-14 md:mb-20">
      <p
        class="text-xs uppercase tracking-[0.15em] text-gray-400 font-medium mb-5"
      >
        {{ page?.eyebrow || "Our Story" }}
      </p>
      <h1
        class="text-4xl md:text-5xl lg:text-6xl font-light text-gray-900 tracking-tight leading-tight mb-5"
      >
        {{ page?.heading || "Built from the ground up" }}
      </h1>
      <p
        class="text-base text-gray-500 font-light leading-relaxed max-w-md mx-auto"
      >
        {{
          page?.subtitle ||
          "How a hill overlooking the Great Zab became the starting point for Kurdistan's next generation of F&B brands."
        }}
      </p>
    </div>

    <!-- Origin Story -->
    <div class="max-w-3xl mx-auto px-6 md:px-8 mb-20 md:mb-28">
      <div class="w-full h-px bg-gray-200 mb-14 md:mb-16"></div>

      <div v-if="page?.storyBody" class="space-y-6">
        <template v-for="block in page.storyBody" :key="block._key">
          <p
            class="text-base md:text-lg text-gray-500 font-light leading-relaxed"
            v-html="renderBlock(block)"
          ></p>
        </template>
      </div>
      <div v-else class="space-y-6">
        <p
          class="text-base md:text-lg text-gray-500 font-light leading-relaxed"
        >
          Banzab is a holding company building the future of food and beverage
          in Kurdistan. We focus on genuine brands that bring change and quality
          to the market — not shortcuts, not trends, but products and
          experiences built to last.
        </p>
        <p
          class="text-base md:text-lg text-gray-500 font-light leading-relaxed"
        >
          Founded in 2019, Banzab started with a simple idea: challenge the norm
          and create brands that are different, forward-thinking, and authentic.
        </p>
        <p
          class="text-base md:text-lg text-gray-500 font-light leading-relaxed"
        >
          The name Banzab reflects both our roots and our vision.
          <span class="text-gray-900">Ban</span> means "top" or "over," and
          <span class="text-gray-900">Zab</span> comes from the Great Zab River
          near the founder's village on the outskirts of Erbil. From a hill
          overlooking the river, the journey of Banzab began — driven by the
          ambition to rise above and build brands that last.
        </p>
      </div>
    </div>

    <!-- Founder -->
    <div
      v-if="page?.founderQuote || showFounderFallback"
      class="max-w-3xl mx-auto px-6 md:px-8 mb-20 md:mb-28"
    >
      <div class="border-t border-b border-gray-200 py-12 md:py-14">
        <div class="grid grid-cols-1 md:grid-cols-12 gap-8 items-center">
          <div class="md:col-span-3">
            <img
              v-if="page?.founderImage"
              :src="
                urlFor(page.founderImage)
                  .width(200)
                  .height(200)
                  .auto('format')
                  .url()
              "
              :alt="page?.founderName || 'Founder'"
              class="w-20 h-20 md:w-24 md:h-24 rounded-full object-cover mx-auto md:mx-0"
            />
            <div
              v-else
              class="w-20 h-20 md:w-24 md:h-24 rounded-full bg-gray-100 mx-auto md:mx-0"
            ></div>
          </div>
          <div class="md:col-span-9 text-center md:text-left">
            <blockquote
              class="text-xl md:text-2xl font-light text-gray-900 leading-snug mb-4"
            >
              "{{
                page?.founderQuote ||
                "We didn't start Banzab to follow trends. We started it to build something real."
              }}"
            </blockquote>
            <div>
              <p class="text-sm text-gray-900 font-medium">
                {{ page?.founderName || "Arkan Yaseen" }}
              </p>
              <p class="text-xs text-gray-400 font-light mt-0.5">
                {{ page?.founderTitle || "Founder & CEO" }}
              </p>
            </div>
          </div>
        </div>
      </div>
    </div>

    <!-- Values -->
    <div
      v-if="displayValues.length"
      class="max-w-3xl mx-auto px-6 md:px-8 mb-20 md:mb-28"
    >
      <p
        class="text-xs uppercase tracking-[0.15em] text-gray-400 font-medium text-center mb-12"
      >
        {{ page?.valuesEyebrow || "What drives us" }}
      </p>

      <div class="space-y-10">
        <template
          v-for="(value, index) in displayValues"
          :key="value._key || index"
        >
          <div v-if="index > 0" class="w-full h-px bg-gray-100"></div>
          <div class="grid grid-cols-1 md:grid-cols-12 gap-4">
            <div class="md:col-span-4">
              <h3 class="text-lg font-light text-gray-900 tracking-tight">
                {{ value.title }}
              </h3>
            </div>
            <div class="md:col-span-8">
              <p class="text-sm text-gray-500 font-light leading-relaxed">
                {{ value.description }}
              </p>
            </div>
          </div>
        </template>
      </div>
    </div>

    <!-- Timeline -->
    <div
      v-if="displayMilestones.length"
      class="max-w-3xl mx-auto px-6 md:px-8 mb-20 md:mb-28"
    >
      <p
        class="text-xs uppercase tracking-[0.15em] text-gray-400 font-medium text-center mb-12"
      >
        {{ page?.timelineEyebrow || "Our journey" }}
      </p>

      <div class="space-y-8">
        <template
          v-for="(milestone, index) in displayMilestones"
          :key="milestone._key || index"
        >
          <div v-if="index > 0" class="w-full h-px bg-gray-100"></div>
          <div class="grid grid-cols-1 md:grid-cols-12 gap-4 items-baseline">
            <div class="md:col-span-3">
              <span class="text-2xl font-light text-gray-900">{{
                milestone.year
              }}</span>
            </div>
            <div class="md:col-span-9">
              <p class="text-sm text-gray-500 font-light leading-relaxed">
                {{ milestone.description }}
              </p>
            </div>
          </div>
        </template>
      </div>
    </div>

    <!-- CTA -->
    <div class="max-w-3xl mx-auto px-6 md:px-8 mb-16 md:mb-20">
      <div class="bg-gray-950 rounded-3xl p-10 md:p-14 text-center">
        <h2
          class="text-3xl md:text-4xl font-light text-white tracking-tight mb-5 leading-tight"
        >
          {{ page?.ctaHeading || "Want to know more?" }}
        </h2>
        <p
          class="text-base text-gray-400 font-light leading-relaxed max-w-md mx-auto mb-8"
        >
          {{
            page?.ctaDescription ||
            "We're always open to conversations about partnerships, opportunities, and the future of F&B in Kurdistan."
          }}
        </p>
        <a
          v-if="isExternalCtaLink"
          :href="page?.ctaButtonLink"
          target="_blank"
          rel="noopener"
          class="inline-flex items-center gap-3 text-white border border-white/30 px-8 py-3.5 rounded-full text-sm font-medium hover:bg-white/10 hover:border-white/50 transition-all"
        >
          <span>{{ page?.ctaButtonText || "Get in Touch" }}</span>
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
              d="M7 17L17 7M17 7H7M17 7v10"
            />
          </svg>
        </a>
        <NuxtLink
          v-else
          :to="page?.ctaButtonLink || '/contact'"
          class="inline-flex items-center gap-3 text-white border border-white/30 px-8 py-3.5 rounded-full text-sm font-medium hover:bg-white/10 hover:border-white/50 transition-all"
        >
          <span>{{ page?.ctaButtonText || "Get in Touch" }}</span>
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
import { useSanityQuery } from "~/composables/useSanity";
import { urlFor } from "~/utils/sanity";

const { data: page } = await useSanityQuery(
  "about-page",
  `*[_type == "aboutPage"][0] {
    eyebrow,
    heading,
    subtitle,
    storyBody,
    founderQuote,
    founderName,
    founderTitle,
    founderImage,
    valuesEyebrow,
    values,
    timelineEyebrow,
    milestones,
    ctaHeading,
    ctaDescription,
    ctaButtonText,
    ctaButtonLink
  }`,
);

const showFounderFallback = computed(() => !page.value);

const isExternalCtaLink = computed(() => {
  const link = page.value?.ctaButtonLink;
  if (!link) return false;
  return link.startsWith("http://") || link.startsWith("https://");
});

const fallbackValues = [
  {
    title: "Quality",
    description:
      "We never lower our standards. Every product, every branch, every decision is measured against the same question: is this the best we can do? If not, we go back and fix it.",
  },
  {
    title: "Innovation",
    description:
      "Kurdistan's market is evolving fast. We stay ahead by constantly rethinking how things are done — from product development to retail experience to how we operate behind the scenes.",
  },
  {
    title: "Growth",
    description:
      "We scale with purpose. Every new branch, every new product, every new brand is a deliberate step — not a rush to expand, but a commitment to growing the right way.",
  },
  {
    title: "Genuineness",
    description:
      "We stay real with our customers and with ourselves. No exaggeration, no hype — just honest products and transparent business practices.",
  },
];

const fallbackMilestones = [
  {
    year: "2019",
    description:
      "Banzab founded. Smoothie Season opens its first branch in Erbil, bringing fresh, high-quality smoothies and juices to Kurdistan for the first time.",
  },
  {
    year: "2020–23",
    description:
      "Rapid expansion across Erbil. Smoothie Season grows to 6 branches, establishing itself as the city's leading smoothie and juice brand.",
  },
  {
    year: "2025",
    description:
      "Pyarra launches — a new line of healthy snacks filling a gap in Kurdistan's market. Smoothie Season's flagship dine-in location begins development at Erbil Avenue.",
  },
  {
    year: "Next",
    description:
      "Continued expansion, new product lines, and a growing portfolio of brands that raise the bar for F&B in the region.",
  },
];

const displayValues = computed(() => {
  return page.value?.values?.length ? page.value.values : fallbackValues;
});

const displayMilestones = computed(() => {
  return page.value?.milestones?.length
    ? page.value.milestones
    : fallbackMilestones;
});

function renderBlock(block) {
  if (!block.children) return "";
  return block.children
    .map((child) => {
      let text = child.text || "";
      text = text
        .replace(/&/g, "&amp;")
        .replace(/</g, "&lt;")
        .replace(/>/g, "&gt;");
      if (child.marks && child.marks.includes("strong")) {
        text = `<strong class="text-gray-900">${text}</strong>`;
      }
      if (child.marks && child.marks.includes("em")) {
        text = `<em>${text}</em>`;
      }
      return text;
    })
    .join("");
}

useHead({
  title: "Our Story - Banzab",
  meta: [
    {
      name: "description",
      content:
        "The story behind Banzab — building the future of food and beverage in Kurdistan from the banks of the Great Zab.",
    },
  ],
});
</script>
