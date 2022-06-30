<template>
  <div class="flex flex-col w-full px-16 justify-center text-gray-700 dark:text-gray-200">
    <!-- Fetch and display the Markdown document from current path -->
    <ContentDoc class="prose prose-gray dark:prose-invert max-w-none py-6 px-6">
      <!-- Slot if document is not found -->
      <template #not-found>
        <div class="flex py-6 px-6 h-80 items-center">
          <h1 class="text-4xl font-bold">
            <Icon name="mdi:magnify" class="w-12 h-12"/> Page not found 
          </h1>
        </div>
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
