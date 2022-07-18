<template>
  <div class="flex flex-col">
    <div class="flex justify-center text-center py-4 md:py-2 text-6xl md:text-7xl font-bold">
      {{ title }}
    </div>
    <div class="flex justify-center text-left text-base mt-2 md:text-lg md:mb-4">
      By {{ author }} | {{ dateDisplay }} {{ tagsDisplay }}
    </div>
    <div class="-mx-12 md:mx-0">
      <img class="object-cover object-center w-full h-64 md:h-96 md:rounded-xl" :src="imagePath" :alt="image">
    </div>
    <div class="-mt-4 -mx-2 md:mx-0 md:mt-0 md:px-32 bg-stone-300 text-neutral-900 dark:bg-neutral-900 dark:text-neutral-100">
      <slot />
    </div>
  </div>
</template>

<script lang="ts">
export default ({
  props: {
    title: {
      type: String,
      default: '',
    },
    date: {
      type: String,
      default: '2022',
    },
    image: {
      type: String,
      default: 'sample',
    },
    author: {
      type: String,
      default: 'Nicholaus Suprapto',
    },
    tags: {
     type: Array,
     default: () => ([]),
    }
  },
  computed: {
    dateDisplay() {
      const date = new Date(this.date);
      return date.toLocaleDateString('en-GB', {
        month: 'long', year: 'numeric'
      });
    },
    tagsDisplay() {
      const tags = this.tags.join(', ');
      if (tags === '') {
        return tags;
      }
      return '| ' + this.tags.join(', ');
    },
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

