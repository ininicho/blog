<template>
  <div class="flex flex-row justify-center md:justify-start md:text-xl">
    <button
      v-if="page > 1"
      class="font-semibold mx-5"
      @click="handlePreviousPage"
    >
      Prev
    </button>
    <button
      v-for="index in prevPages"
      :key="index"
      class="mx-5"
      @click="handleChangePage(index)"
    >
      {{ index }}
    </button>
    <button class="font-semibold mx-5 underline">
      {{ page }}
    </button>
    <button
      v-for="index in nextPages"
      :key="index"
      class="mx-5"
      @click="handleChangePage(index + page)"
    >
      {{ index + page }}
    </button>
    <button
      v-if="page != totalPages"
      class="font-semibold mx-5"
      @click="handleNextPage"
    >
      Next
    </button>
  </div>
</template>

<script lang="ts">
export default {
  name: 'StoriesPagination',
  emits: ['change-page'],
  props: {
    page: {
      type: Number,
      required: true
    },
    totalPages: {
      type: Number,
      required: true
    }
  },
  computed: {
    prevPages () {
      return this.page - 1
    },
    nextPages () {
      return this.totalPages - this.page
    }
  },
  methods: {
    handlePreviousPage () {
      this.$emit('change-page', this.page - 1)
    },
    handleNextPage () {
      this.$emit('change-page', this.page + 1)
    },
    handleChangePage (index) {
      this.$emit('change-page', index)
    }
  }
}
</script>
