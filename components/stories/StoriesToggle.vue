<template>
  <div class="flex flex-row justify-between mt-14 md:mt-28 py-7 text-gray-500 dark:text-gray-200">
    <div class="flex flex-row md:basis-1/2 items-center">
      <NuxtLink to="/about">
        <div class="w-10 h-10 mx-3">
          <img src="@/static/profile.jpg" alt="Cover" class="rounded-full w-10 h-10">
        </div>
      </NuxtLink>
      <div class="flex flex-wrap">
        <p class="text-xs md:text-lg">
          Writing and translating my thoughts into words and code.
          I built this blog as a medium to share all my stories.
        </p>
      </div>
    </div>
    <div class="hidden items-center justify-center md:flex md:flex-row md:w-1/5">
      <button @click="$emit('change-layout', 'grid')">
        <Icon name="heroicons-outline:template" class="w-7 h-7 mx-4" />
      </button>
      <button @click="$emit('change-layout', 'list')">
        <Icon name="heroicons-outline:view-list" class="w-7 h-7 mx-4" />
      </button>
    </div>
  </div>
</template>
