<template>
  <div>
    <h1 class="uppercase text-xl font-semibold text-gray-400 mb-4">Additional Links</h1>
    <div class="space-y-5">
    <AppAddition
      v-for="item in pdfs"
      :key="item.title"
      :title="item.title"
      :url="item.link"
      class="flex items-end gap-4  dark:text-gray-300 dark:hover:text-black dark:hover:bg-white group dark:bg-black ring-1 dark:ring-white bg-white text-black hover:bg-black hover:text-white ring-black"
    />
    </div>
  </div>
</template>

<script lang="ts" setup>
  const pdfs = [
  {
    title: 'Resume',
    link: 'https://drive.google.com/drive/folders/1s67KaIRQ4ytVOxSsNSK3bOCjIcZmpeQZ?usp=sharing'
  },
  {
    title: 'Certification',
    link: 'https://drive.google.com/drive/folders/19-Co4wwquYC2OMndzDmIkeaTOCZwMxF5?usp=sharing'
  }
]
</script>

<style>

</style>