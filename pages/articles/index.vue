<template>
  <section class="space-y-6 py-10">
    <AppHeader class="mb-16" title="Projects" :description="description" />
    <ul class="space-y-4">
      <li v-for="article in paginatedArticles" :key="article._path">
        <AppArticleCard :article="article" />
      </li>
    </ul>

    <div class="flex justify-center pt-6">
      <UPagination
        v-model="page"
        :total="total"
        :page-count="perPage"
      />
    </div>
  </section>
</template>
<script setup>
const page = ref(1);
const perPage = 5
const description =
  "All of my projects wrapped in articles";
useSeoMeta({
  title: "Projects | Baskoro Aji",
  description,
});

const { data: articles } = await useAsyncData("all-articles", () =>
  queryContent("/articles").sort({ published: -1 }).find()
);
const total = computed(() => articles.value?.length || 0);

const paginatedArticles = computed (() => articles.value.slice((page.value - 1) * perPage, page.value * perPage)) ?? [];
</script>
