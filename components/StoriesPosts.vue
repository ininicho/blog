<template>
  <NuxtLink to="/" class="flex flex-col px-10 py-10">
    <div class="overflow-clip max-h-96 rounded-2xl">
      <img :src="image" :alt="title">
    </div>
    <p class="text-4xl font-bold mt-6">
      {{ title }}
    </p>
    <p class="text-lg mt-3">
      {{ description }}
    </p>
    <div class="flex flex-row justify-between items-center mt-3">
      <p class="text-xl font-semibold">
        {{ date }}
      </p>
      <p class="text-md font-semibold">
        <Icon name="mdi:book-open-page-variant" class="mb-1 mr-1" />
        {{ time }} min read
      </p>
    </div>
  </NuxtLink>
</template>

<script lang="ts">

export default ({
  props: {
    title: {
      type: String,
      required: true
    },
    description: {
      type: String,
      required: true
    },
    image: {
      type: String,
      required: true
    },
    date: {
      type: String,
      required: true
    },
    time: {
      type: Number,
      required: true
    }
  }
})

</script>

<style scoped>

</style>
