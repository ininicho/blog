<script setup lang="ts">
import biocard from '@/static/biocard.jpg'
const bioCardContent = await queryContent()
  .where({ title: 'BioCard' })
  .findOne()
</script>

<template>
  <div class="flex flex-col md:flex-row flex-wrap justify-between md:pt-7 text-gray-500 dark:text-gray-200">
    <div class="md:basis-3/5 mb-5 md:pr-28 md:text-2xl md:py-10">
      <ContentRenderer :value="bioCardContent" unwrap="p" />
    </div>
    <div class="py-5 md:basis-2/5 md:px-7">
      <img :src="biocard" alt="Cover" class="object-cover rounded-3xl">
    </div>
  </div>
</template>
