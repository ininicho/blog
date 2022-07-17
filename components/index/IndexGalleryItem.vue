<template>
  <div class="flex flex-col py-3 md:py-6 md:px-6">
    <div class="flex mb-5">
      <img :src="item.image" :alt="item.title" class="object-cover rounded-2xl">
    </div>
    <div class="flex flex-col justify-center my-4">
      <p class="text-xl md:text-3xl font-semibold">
        {{ item.title }}
      </p>
      <p class="text-md text-justify my-2">
        {{ item.description }}
      </p>
      <NuxtLink :to="item.link" class="flex items-center text-md font-bold">
        <Icon :name="item.icon" class="mr-2" /> 
        {{ item.article }}
        <Icon name="material-symbols:arrow-right-alt-rounded" class="ml-1" />
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
