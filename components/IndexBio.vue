<script setup lang="ts">
import biocard from '@/static/biocard.jpg'
const bioCardContent = await queryContent()
  .where({ title: 'BioCard' })
  .findOne()
</script>

<template>
  <div class="flex flex-col md:flex-row flex-wrap justify-between py-7 text-gray-500 dark:text-gray-200">
    <div class="lg:basis-3/5 lg:pr-28 text-2xl py-10">
      <ContentRenderer :value="bioCardContent" unwrap="p" />
    </div>
    <div class="basis-2/5 px-7">
      <img :src="biocard" alt="Cover" class="object-cover rounded-3xl">
    </div>
  </div>
</template>
