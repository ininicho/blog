<template>
  <div class="flex flex-col justify-center py-6 px-6">
    <div class="flex mb-5">
      <img :src="item.image" :alt="item.title" class="object-cover rounded-2xl">
    </div>
    <div class="flex flex-col justify-center my-5">
      <p class="text-3xl font-semibold">
        {{ item.title }}
      </p>
      <p class="text-md">
        {{ item.description }}
      </p>
      <NuxtLink to="{{ item.link }}" class="flex items-center text-md font-bold">
        {{ item.article }} <Icon name="material-symbols:arrow-right-alt-rounded" class="ml-1" />
      </NuxtLink>
    </div>
  </div>
</template>

<script lang="ts">
export default {
  props: {
    item: {
      type: Object,
      required: true
    }
  }
}
</script>
