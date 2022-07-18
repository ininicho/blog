<script setup lang="ts">
import StoriesToggle from './StoriesToggle.vue'
import StoriesPosts from './StoriesPosts.vue'
import StoriesPagination from './StoriesPagination.vue'

// eslint-disable-next-line @typescript-eslint/no-unused-vars
const stories = await queryContent()
  .where({ type: 'story' })
  .sort({ date: -1 })
  .find()
</script>

<template>
  <div class="mb-4 md:mb-10">
    <StoriesToggle
      @change-layout="handleChangeLayout"
    />
    <div
      :class="layout === 'grid' ? 'md:grid-cols-2' : 'md:grid-cols-1'"
      class="grid grid-cols-1 grid-flow-row md:mt-10 md:mb-5"
    >
      <StoriesPosts
        v-for="(story, index) in storiesPaginated[page - 1]"
        :key="index"
        :story="story"
      />
    </div>
    <StoriesPagination
      v-if="totalPages > 1"
      :page="page"
      :total-pages="totalPages"
      @change-page="handleChangePage"
    />
  </div>
</template>

<script lang="ts">
export default {
  data () {
    return {
      page: 1,
      totalPages: Math.ceil(this.stories.length / 4),
      storiesPaginated: this.paginateStories(this.stories),
      layout: 'grid'
    }
  },
  methods: {
    handleChangePage (page) {
      this.page = page
    },
    paginateStories (stories) {
      const storiesPaginated = []
      const itemsPerPage = 4
      for (let i = 0; i < stories.length; i += itemsPerPage) {
        const chunk = stories.slice(i, i + itemsPerPage)
        storiesPaginated.push(chunk)
      }
      return storiesPaginated
    },
    handleChangeLayout (layout) {
      this.layout = layout
    }
  }
}
</script>
