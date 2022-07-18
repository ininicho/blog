<template>
  <div class="px-12 md:px-16 pt-10 mb-4 sm:px-8">
    <!-- Fetch and display the Markdown document from current path -->
    <ContentDoc class="prose prose-neutral dark:prose-invert max-w-none text-xl text-justify leading-relaxed">
      <!-- Slot if document is not found -->
      <template #not-found>
        <h1 class="text-2xl">
          Page not found
        </h1>
      </template>
    </ContentDoc>
  </div>
</template>

<style lang="postcss">
/* Customize headers to remove default underline */
.prose h2 a,
.prose h3 a {
  @apply no-underline;
  &:hover {
    @apply border-b border-neutral-600 dark:border-neutral-300;
  }
}
</style>
