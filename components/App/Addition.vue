<template>
  <UButton
    :label="title"
    color="primary"
    variant="solid"
    @click="openPdf"
  />
</template>

<script lang="ts" setup>
  const props = defineProps({
    title: String,
    url: String
  })

  function openPdf(){
    window.open(props.url, '_blank');
  }
</script>

<style>

</style>