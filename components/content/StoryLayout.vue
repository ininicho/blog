<template>
  <div class="flex flex-col px-16">
    <div class="flex justify-center py-2 text-7xl font-bold">
      {{ title }}
    </div>
    <div class="flex justify-center text-lg mb-4">
      By {{ author }} | {{ dateDisplay }} {{ tagsDisplay }}
    </div>
    <img class="object-cover object-center w-full h-96 rounded-xl" :src="imagePath" :alt="image">
    <div class="px-32">
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

