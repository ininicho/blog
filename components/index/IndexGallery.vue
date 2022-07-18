<template>
  <div class="flex-col flex-wrap md:py-7 mt-5 md:mb-10 items-center">
    <p class="text-3xl md:text-4xl md:pl-5 font-semibold">
      🧑‍💻 Latest Works
    </p>
    <div class="grid grid-cols-1 lg:grid-cols-3 pt-6">
      <IndexGalleryItem
        v-for="(item, index) in items"
        :key="index"
        :item="item"
      />
    </div>
  </div>
</template>

<script lang="ts">
import GalleryItems from '@/assets/projects.json'
export default {
  data () {
    return {
      items: GalleryItems
    }
  }
}
</script>
