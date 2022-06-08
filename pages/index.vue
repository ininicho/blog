<script setup lang="ts">
definePageMeta({
  title: 'Home'
})

// const contentQuery = await queryContent().limit(5).find()
</script>

<template>
  <div class="flex flex-col justify-center px-16">
    <Hero />
    <BioSection />
    <BioCard />
  </div>
</template>
