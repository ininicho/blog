<script setup lang="ts">
const bioCardContent = await queryContent()
  .where({ title: 'BioCard' })
  .findOne()
</script>

<template>
  <div class="flex flex-col md:flex-row flex-wrap justify-between py-7 text-gray-500 dark:text-gray-200">
    <div class="md:basis-3/5 md:pr-28">
      <p class="text-2xl py-10">
        <ContentRenderer :value="bioCardContent" unwrap="p" />
      </p>
    </div>
    <div class="md:basis-2/5 px-7">
      <img src="/assets/biocard.jpg" alt="Cover" class="rounded-3xl">
    </div>
  </div>
</template>
