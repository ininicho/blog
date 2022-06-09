<script setup lang="ts">
const content = "I'm a student in the University of Waterloo studying Computer Science. Coffee lover and data enthusiast."
</script>

<template>
  <div class="flex flex-row flex-wrap justify-between py-7 text-gray-500 dark:text-gray-200">
    <div class="flex flex-row md:basis-1/2 items-center">
      <NuxtLink to="/about">
        <div class="w-10 h-10 mx-3">
          <img src="/assets/profile.jpg" alt="Cover" class="rounded-full w-10 h-10">
        </div>
      </NuxtLink>
      <div class="flex flex-wrap">
        <p class="text-md">
          {{ content }}
        </p>
      </div>
    </div>
    <div class="hidden items-center justify-center hover:text-gray-700 dark:hover:text-gray-300 md:flex md:flex-row md:basis-1/5">
      <a href="/"><Icon name="mdi:twitter" class="mx-4" /></a>
      <a href="/"><Icon name="mdi:linkedin" class="mx-4" /></a>
      <a href="/"><Icon name="mdi:github" class="mx-4" /></a>
      <a href="/"><Icon name="mdi:instagram" class="mx-4" /></a>
      <a href="/"><Icon name="ic:outline-discord" class="mx-4" /></a>
      <a href="/"><Icon name="material-symbols:person-pin" class="mx-4" /></a>
    </div>
  </div>
</template>
