<template>
  <div v-if="article" class="pt-14 md:pt-16">
    <!-- Article Header - Centered -->
    <div class="max-w-3xl mx-auto px-6 md:px-8 text-center mb-12 md:mb-16">
      <div class="flex items-center justify-center gap-3 mb-6">
        <time
          :datetime="article.date"
          class="text-[11px] uppercase tracking-[0.12em] text-gray-400 font-medium"
        >
          {{ formatDate(article.date) }}
        </time>
        <span
          v-if="article.category"
          class="w-1 h-1 rounded-full bg-gray-300"
        ></span>
        <span
          v-if="article.category"
          class="text-[11px] uppercase tracking-[0.12em] text-gray-400 font-medium"
        >
          {{ article.category }}
        </span>
      </div>

      <h1
        class="text-3xl md:text-4xl lg:text-5xl font-light text-gray-900 tracking-tight leading-tight mb-6"
      >
        {{ article.title }}
      </h1>

      <p
        v-if="article.description"
        class="text-base md:text-lg text-gray-500 font-light leading-relaxed max-w-xl mx-auto mb-6"
      >
        {{ article.description }}
      </p>

      <p v-if="article.author" class="text-xs text-gray-400 font-light">
        By {{ article.author }}
      </p>
    </div>

    <!-- Divider -->
    <div class="max-w-3xl mx-auto px-6 md:px-8">
      <div class="w-full h-px bg-gray-200 mb-12 md:mb-14"></div>
    </div>

    <!-- Article Body -->
    <div class="max-w-2xl mx-auto px-6 md:px-8 mb-20 md:mb-28">
      <article class="article-content">
        <ContentRenderer :value="article" />
      </article>
    </div>

    <!-- Related Articles -->
    <div
      v-if="relatedArticles.length > 0"
      class="max-w-3xl mx-auto px-6 md:px-8 mb-16 md:mb-20"
    >
      <div class="border-t border-gray-200 pt-12 md:pt-14">
        <p
          class="text-xs uppercase tracking-[0.15em] text-gray-400 font-medium text-center mb-10"
        >
          More from the newsroom
        </p>
        <div>
          <article
            v-for="related in relatedArticles"
            :key="related._path"
            class="group cursor-pointer border-b border-gray-200 py-8 md:py-10"
            @click="navigateToArticle(related._path)"
          >
            <div class="flex items-center gap-3 mb-3">
              <time
                :datetime="related.date"
                class="text-[11px] uppercase tracking-[0.12em] text-gray-400 font-medium"
              >
                {{ formatDate(related.date) }}
              </time>
              <span
                v-if="related.category"
                class="w-1 h-1 rounded-full bg-gray-300"
              ></span>
              <span
                v-if="related.category"
                class="text-[11px] uppercase tracking-[0.12em] text-gray-400 font-medium"
              >
                {{ related.category }}
              </span>
            </div>
            <h3
              class="text-xl md:text-2xl font-light text-gray-900 tracking-tight leading-snug mb-2 group-hover:text-gray-500 transition-colors"
            >
              {{ related.title }}
            </h3>
            <p class="text-sm text-gray-500 font-light leading-relaxed">
              {{ related.description }}
            </p>
          </article>
        </div>
      </div>
    </div>
  </div>

  <!-- 404 -->
  <div v-else class="pt-14 md:pt-16">
    <div class="max-w-3xl mx-auto px-6 md:px-8 py-20 text-center">
      <h1
        class="text-3xl md:text-4xl font-light text-gray-900 tracking-tight mb-5"
      >
        Article not found
      </h1>
      <p class="text-base text-gray-500 font-light mb-8">
        The article you're looking for doesn't exist or has been moved.
      </p>
      <NuxtLink
        to="/newsroom"
        class="inline-block bg-gray-900 text-white px-8 py-3.5 text-sm font-medium hover:bg-gray-800 transition-colors rounded-full"
      >
        Browse Newsroom
      </NuxtLink>
    </div>
  </div>
</template>

<script setup>
const route = useRoute();
const slug = Array.isArray(route.params.slug)
  ? route.params.slug.join("/")
  : route.params.slug;

const { data: article } = await useAsyncData(route.path, async () => {
  try {
    const allArticles = await queryCollection("newsroom").all();

    const foundArticle = allArticles.find((a) => {
      const stemFilename = a.stem ? a.stem.split("/").pop() : "";
      const titleSlug = a.title
        .toLowerCase()
        .replace(/[^a-z0-9]+/g, "-")
        .replace(/(^-|-$)/g, "");
      return stemFilename === slug || titleSlug === slug;
    });

    if (foundArticle) {
      foundArticle._path = `/newsroom/${slug}`;
    }

    return foundArticle;
  } catch (err) {
    console.error("Error fetching newsroom article:", err);
    return null;
  }
});

const { data: allArticles } = await useAsyncData("all-newsroom-articles", () =>
  queryCollection("newsroom").sort({ date: -1 }).limit(3).find(),
);

const relatedArticles = computed(() => {
  if (!allArticles.value || !article.value) return [];
  return allArticles.value
    .filter((a) => a.title !== article.value.title)
    .map((a) => {
      const articleSlug = a.stem
        ? a.stem.split("/").pop()
        : a.title
            .toLowerCase()
            .replace(/[^a-z0-9]+/g, "-")
            .replace(/(^-|-$)/g, "");
      return {
        ...a,
        _path: `/newsroom/${articleSlug}`,
      };
    })
    .slice(0, 2);
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

useHead({
  title: computed(() =>
    article.value
      ? `${article.value.title} - Banzab`
      : "Article Not Found - Banzab",
  ),
  meta: computed(() => [
    {
      name: "description",
      content: article.value ? article.value.description : "Article not found",
    },
  ]),
});
</script>

<style>
.article-content h2 {
  font-size: 1.5rem;
  font-weight: 300;
  color: #111827;
  letter-spacing: -0.025em;
  margin-top: 2.5rem;
  margin-bottom: 1rem;
}

.article-content h3 {
  font-size: 1.25rem;
  font-weight: 300;
  color: #111827;
  letter-spacing: -0.025em;
  margin-top: 2rem;
  margin-bottom: 0.75rem;
}

.article-content p {
  font-size: 1.05rem;
  font-weight: 300;
  color: #6b7280;
  line-height: 1.85;
  margin-bottom: 1.25rem;
}

.article-content ul,
.article-content ol {
  font-size: 1.05rem;
  font-weight: 300;
  color: #6b7280;
  line-height: 1.85;
  margin-bottom: 1.25rem;
  padding-left: 1.5rem;
}

.article-content li {
  margin-bottom: 0.5rem;
}

.article-content strong {
  font-weight: 500;
  color: #111827;
}

.article-content blockquote {
  border-left: 2px solid #e5e7eb;
  padding-left: 1.5rem;
  margin: 2rem 0;
  font-style: italic;
  color: #9ca3af;
}

.article-content a {
  color: #111827;
  text-decoration: underline;
  text-underline-offset: 2px;
}

.article-content a:hover {
  color: #6b7280;
}

.article-content hr {
  border: none;
  border-top: 1px solid #e5e7eb;
  margin: 2.5rem 0;
}
</style>
