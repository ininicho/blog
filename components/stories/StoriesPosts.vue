<template>
  <NuxtLink :to="story._path" class="flex flex-col md:px-10 py-10">
    <img class="object-cover object-center w-full h-96 rounded-2xl" :src="imagePath" :alt="story.image">
    <p class="text-3xl md:text-4xl font-bold mt-6">
      {{ story.title }}
    </p>
    <p class="text-base md:text-lg mt-3">
      {{ story.description }}
    </p>
    <div class="flex flex-row justify-between items-center mt-3">
      <p class="text-lg md:text-xl font-semibold">
        {{ story.date.replace(/\T.*/, '') }}
      </p>
      <p class="text-md font-semibold">
        <Icon name="mdi:book-open-page-variant" class="hidden md:inline mb-1 mr-1" />
        {{ 10 }} min read
      </p>
    </div>
  </NuxtLink>
</template>

<script lang="ts">
export default ({
  props: {
    story: {
      type: Object,
      required: true
    }
  },
  data () {
    return {
      imagePath: null
    }
  },
  async mounted () {
    await this.importImage(this.story.image)
  },
  async updated () {
    await this.importImage(this.story.image)
  },
  methods: {
    async importImage (image) {
      const img = await import(`../../static/${image}.jpg`)
      this.imagePath = img.default
    }
  }
})
</script>
