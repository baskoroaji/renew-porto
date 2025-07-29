<!-- components/Timeline.vue -->
<template>
  <div class="relative border-l border-gray-300 dark:border-gray-600 ml-4">
    <div
      v-for="(event, index) in items"
      :key="index"
      class="mb-10 ml-6 relative"
    >

      <!-- Card -->
      <UCard>
        <template #header>
          <div class="text-sm text-gray-400 dark:text-gray-500">
            {{ event.date }}
          </div>
        </template>

        <h3 class="font-semibold text-gray-900 dark:text-white text-lg">
          {{ event.title }}
        </h3>
        <p class="uppercase text-xs font-semibold text-gray-400 mb-4">
          {{ event.description }}
        </p>

        <template #footer v-if="event.tags?.length">
          <div class="flex gap-2 flex-wrap mt-2">
            <UBadge
              v-for="(tag, tagIndex) in event.tags"
              :key="tagIndex"
              color="gray"
              variant="subtle"
            >
              {{ tag }}
            </UBadge>
          </div>
        </template>
      </UCard>
    </div>
  </div>
</template>

<script setup>
const props = defineProps({
  items: {
    type: Array,
    required: true
  }
});
</script>
