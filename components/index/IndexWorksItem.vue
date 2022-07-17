<template>
  <div v-if="work.show" class="flex flex-row md:px-5 py-4 my-4">
    <div class="hidden md:basis-1/3 md:flex pr-5 justify-center items-baseline">
      <img :src="image" :alt="work.image" class="object-cover">
    </div>
    <div class="flex flex-col basis-2/3 md:px-2">
      <p class="text-xl md:text-3xl my-1 font-semibold">
        {{ work.title }}
      </p>
      <p class="text-lg font-medium">
        {{ work.description }}
      </p>
      <p class="text-md text-justify leading-relaxed my-2">
        {{ work.text }}
      </p>
      <p class="text-md font-bold">
        <a :href="work.url">{{ work.link }}<Icon name="material-symbols:arrow-right-alt-rounded" /></a>
      </p>
    </div>
  </div>
</template>

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
    const img = await import(`../../static/${this.work.image}.jpg`)
    this.image = img.default
  }
}
</script>

