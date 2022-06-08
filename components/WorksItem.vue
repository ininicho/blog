<script lang="ts">
export default {
  props: {
    work: {
      type: Object,
      required: true
    }
  }
}
</script>

<template>
  <div v-if="work.show" class="grid grid-cols-5 grid-rows-2 gap-5 h-80 pr-12">
    <div class="justify-center items-center">
      <img :src="work.image" :alt="work.title" class="object-cover">
    </div>
    <div class="col-span-4 pl-1">
      <div class="flex flex-wrap">
        <p class="text-2xl">
          {{ work.title }}
        </p>
        <p class="text-md">
          {{ work.description }}
        </p>
        <p class="text-sm">
          {{ work.text }}
        </p>
      </div>
    </div>
  </div>
</template>
