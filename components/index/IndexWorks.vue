<script lang="ts">
import worksContent from '@/assets/works.json'
export default {
  data () {
    return {
      works: worksContent
    }
  }
}
</script>

<template>
  <div class="flex-col flex-wrap mt-5 py-3 md:py-7 items-center">
    <div class="text-3xl md:text-4xl md:pl-5 font-semibold">
      📌 Experiences
    </div>
    <div class="grid grid-cols-1 md:grid-cols-2 md:pt-10">
      <IndexWorksItem
        v-for="(work, index) in works"
        :key="index"
        :work="work"
      />
    </div>
  </div>
</template>
