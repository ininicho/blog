<script lang="ts">
import worksContent from '../assets/works.json'
export default {
  data () {
    return {
      works: worksContent
    }
  }
}
</script>

<template>
  <div class="flex-col flex-wrap py-7 mt-5 items-center text-gray-700 dark:text-gray-200">
    <div class="flex">
      <p class="text-4xl pl-5 font-semibold">
        Experiences
      </p>
    </div>
    <div class="grid grid-cols-1 md:grid-cols-2 pt-10 box-content">
      <IndexWorksItem
        v-for="(work, index) in works"
        :key="index"
        :work="work"
      />
    </div>
  </div>
</template>
