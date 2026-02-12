<template>
  <div class="pt-14 md:pt-16">
    <!-- Header -->
    <div class="max-w-4xl mx-auto px-6 md:px-8 mb-16 md:mb-24">
      <div class="grid grid-cols-1 md:grid-cols-12 gap-10 md:gap-8 items-end">
        <div class="md:col-span-7">
          <p
            class="text-xs uppercase tracking-[0.15em] text-gray-400 font-medium mb-5"
          >
            Newsroom
          </p>
          <h1
            class="text-4xl md:text-5xl lg:text-6xl font-light text-gray-900 tracking-tight leading-tight mb-6"
          >
            Latest updates
          </h1>
          <p
            class="text-base md:text-lg text-gray-500 font-light leading-relaxed max-w-xl"
          >
            News, insights, and updates from Banzab and our portfolio companies.
          </p>
        </div>
      </div>
    </div>

    <!-- Loading -->
    <div
      v-if="pending"
      class="max-w-4xl mx-auto px-6 md:px-8 py-20 text-center"
    >
      <div
        class="inline-block animate-spin rounded-full h-6 w-6 border-b-2 border-gray-900"
      ></div>
    </div>

    <!-- Error -->
    <div
      v-else-if="error"
      class="max-w-6xl mx-auto px-6 md:px-8 py-20 text-center"
    >
      <p class="text-gray-500 font-light">Unable to load articles.</p>
    </div>

    <!-- Articles -->
    <div v-else class="max-w-4xl mx-auto px-6 md:px-8 mb-16 md:mb-20">
      <div v-if="newsArticles.length === 0" class="py-20 text-center">
        <p class="text-gray-500 font-light">No articles yet.</p>
      </div>

      <div v-else>
        <!-- Featured / First Article -->
        <article
          v-if="newsArticles[0]"
          class="group cursor-pointer mb-16 md:mb-20"
          @click="navigateToArticle(newsArticles[0]._path)"
        >
          <div class="border-b border-gray-200 pb-12 md:pb-16">
            <div class="flex items-center gap-3 mb-5">
              <time
                :datetime="newsArticles[0].date"
                class="text-[11px] uppercase tracking-[0.12em] text-gray-400 font-medium"
              >
                {{ formatDate(newsArticles[0].date) }}
              </time>
              <span class="w-1 h-1 rounded-full bg-gray-300"></span>
              <span
                v-if="newsArticles[0].category"
                class="text-[11px] uppercase tracking-[0.12em] text-gray-900 font-medium"
              >
                {{ newsArticles[0].category }}
              </span>
            </div>
            <h2
              class="text-3xl md:text-4xl lg:text-5xl font-light text-gray-900 tracking-tight leading-tight mb-5 group-hover:text-gray-600 transition-colors"
            >
              {{ newsArticles[0].title }}
            </h2>
            <p
              class="text-base md:text-lg text-gray-500 font-light leading-relaxed max-w-2xl mb-6"
            >
              {{ newsArticles[0].description }}
            </p>
            <span
              class="inline-flex items-center gap-2 text-sm text-gray-900 font-medium group-hover:text-gray-600 transition-colors"
            >
              <span>Read article</span>
              <svg
                class="w-4 h-4 group-hover:translate-x-0.5 transition-transform"
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
            </span>
          </div>
        </article>

        <!-- Rest of Articles -->
        <div class="space-y-0">
          <article
            v-for="article in newsArticles.slice(1)"
            :key="article._path"
            class="group cursor-pointer"
            @click="navigateToArticle(article._path)"
          >
            <div
              class="border-b border-gray-200 py-8 md:py-10 grid grid-cols-1 md:grid-cols-12 gap-4 md:gap-8 items-start"
            >
              <!-- Date -->
              <div class="md:col-span-3">
                <time
                  :datetime="article.date"
                  class="text-[11px] uppercase tracking-[0.12em] text-gray-400 font-medium"
                >
                  {{ formatDate(article.date) }}
                </time>
                <span
                  v-if="article.category"
                  class="block text-[11px] uppercase tracking-[0.12em] text-gray-900 font-medium mt-1"
                >
                  {{ article.category }}
                </span>
              </div>
              <!-- Content -->
              <div class="md:col-span-7">
                <h2
                  class="text-xl md:text-2xl font-light text-gray-900 tracking-tight leading-snug mb-2 group-hover:text-gray-600 transition-colors"
                >
                  {{ article.title }}
                </h2>
                <p class="text-sm text-gray-500 font-light leading-relaxed">
                  {{ article.description }}
                </p>
              </div>
              <!-- Arrow -->
              <div class="md:col-span-2 hidden md:flex justify-end pt-1">
                <svg
                  class="w-4 h-4 text-gray-300 group-hover:text-gray-900 group-hover:translate-x-0.5 transition-all"
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
              </div>
            </div>
          </article>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
useHead({
  title: "Newsroom - Banzab",
  meta: [
    {
      name: "description",
      content:
        "Stay up to date with the latest news, insights, and updates from Banzab and our portfolio companies.",
    },
  ],
});

const {
  data: newsArticles,
  pending,
  error,
} = await useAsyncData("newsroom", async () => {
  try {
    const result = await queryCollection("newsroom").all();
    return result
      .map((article) => {
        const slug = article.stem
          ? article.stem.split("/").pop()
          : article.title
              .toLowerCase()
              .replace(/[^a-z0-9]+/g, "-")
              .replace(/(^-|-$)/g, "");
        return {
          ...article,
          _path: `/newsroom/${slug}`,
        };
      })
      .sort((a, b) => new Date(b.date) - new Date(a.date));
  } catch (err) {
    console.error("Query error:", err);
    throw err;
  }
});

function navigateToArticle(path) {
  navigateTo(path);
}

function formatDate(dateString) {
  const date = new Date(dateString);
  return date.toLocaleDateString("en-US", {
    year: "numeric",
    month: "long",
    day: "numeric",
  });
}
</script>
