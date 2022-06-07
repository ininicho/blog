<script setup lang="ts">
definePageMeta({
  layout: false,
  title: 'Home',
});

const contentQuery = await queryContent().limit(5).find();
</script>

<template>
  <NuxtLayout name="default">
    <Hero />
    <div class="max-w-2xl px-4 py-10 m-auto bg-white sm:px-8 sm:shadow dark:bg-gray-800 sm:rounded">
      <ul>
          <li v-for="post in contentQuery">
              <NuxtLink :to="`/posts/${post.slug}`">
              {{ post.title }}
              </NuxtLink>
          </li>
      </ul>
    </div>
  </NuxtLayout>
</template>

<style lang="postcss">
body {
  @apply bg-gray-50 dark:bg-gray-900;
}
</style>