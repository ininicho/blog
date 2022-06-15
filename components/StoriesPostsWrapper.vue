<template>
  <div class="grid grid-cols-1 md:grid-cols-2 grid-flow-row my-10">
    <StoriesPosts
      v-for="index in 4"
      :key="index"
      :title="title"
      :description="description"
      :image="image"
      :date="date"
      :time="time"
    />
  </div>
</template>

<script setup lang="ts">
const title = 'Island in Japan'
const description = `A journey to the island of Japan with strangers.
      I spent a few months in the island of Japan.
      I met some friends and learned a lot about the culture and the people.`
const image = '@/static/islandjapan.jpg'
const date = 'June 10, 2022'
const time = 10
</script>
