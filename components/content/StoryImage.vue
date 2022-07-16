<template>
  <div class="flex justify-center">
    <img class="w-5/6 rounded" :src="imagePath" :alt="image">
  </div>
</template>

<script lang="ts">
export default ({
  props: {
    image: {
      type: String,
      required: true,
    }
  },
  data() {
    return {
      imagePath: null,
    }
  },
  async mounted() {
    await this.importImage(this.image);
  },
  methods: {
    async importImage (image) {
      const img = await import(`../../static/${image}.jpg`)
      this.imagePath = img.default
    }
  }
})
</script>

