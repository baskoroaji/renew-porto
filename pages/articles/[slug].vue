<template>
  <main class="min-h-screen">
    <div
      class="prose dark:prose-invert prose-blockquote:not-italic prose-pre:bg-gray-900 prose-img:ring-1 prose-img:ring-gray-200 dark:prose-img:ring-white/10 prose-img:rounded-lg"
    >
      <ContentDoc :path="`/articles/${route.params.slug}`" v-slot="{ doc }">
  <article v-if="doc">
    <h1>{{ doc.title }}</h1>
    <h3>By {{  doc.author }}</h3>
    
    <ContentRenderer :value="doc" />
  </article>
</ContentDoc>
    </div>
  </main>
</template>
<script setup>
const route = useRoute();
</script>
<style>
</style>
