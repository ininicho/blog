<script setup lang="ts">
const contentQuery = await queryContent().limit(5).find();
</script>

<template>
  <div class="max-w-2xl px-4 py-10 m-auto bg-white sm:px-8 sm:shadow dark:bg-gray-800 sm:rounded">
    <ul>
        <li v-for="post in contentQuery">
            <NuxtLink :to="post._path">
            {{ post.title }}
            </NuxtLink>
        </li>
    </ul>
  </div>
</template>