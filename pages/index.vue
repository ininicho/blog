<script setup lang="ts">
definePageMeta({
  title: 'Home',
});

const contentQuery = await queryContent().limit(5).find();
console.log(contentQuery.map(c => c._path));
</script>

<template>
  <div class="flex flex-col justify-center px-16">
    <Hero />
    <BioSection />
    <BioCard />
  </div>
</template>