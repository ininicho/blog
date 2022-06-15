<script lang="ts">
export default {
  props: {
    work: {
      type: Object,
      required: true
    }
  },
  data () {
    return {
      image: null
    }
  },
  async mounted () {
    const img = await import(`../static/${this.work.image}.jpg`)
    this.image = img.default
  }
}
</script>

<template>
  <div v-if="work.show" class="flex flex-row px-5 py-5">
    <div class="hidden md:flex pr-5 justify-center items-baseline">
      <img :src="image" :alt="work.image" class="object-cover">
    </div>
    <div class="flex flex-col px-2">
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
        <p class="text-md font-bold">
          <a href="work.url">{{ work.link }}<Icon name="material-symbols:arrow-right-alt-rounded" /></a>
        </p>
      </div>
    </div>
  </div>
</template>
