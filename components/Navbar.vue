<template>
  <div class="flex justify-between px-6 py-6 mx-auto">
    <!-- Brand -->
    <div class="flex items-center font-sans text-gray-700 dark:text-gray-200">
      <NuxtLink to="/"><strong>Nicholaus Suprapto</strong></NuxtLink>
    </div>

    <!-- Navigation -->
    <div class="flex items-center">
      <div class="text-gray-500 dark:text-gray-200 align-center items-center">
        <ContentNavigation v-slot="{ navigation }">
          <NuxtLink
            v-for="link of navigation"
            :key="link._path"
            :to="link._path"
            active-class="font-bold"
            class="mr-4"
          >
            {{ link.navTitle || link.title }}
          </NuxtLink>
        </ContentNavigation>
      </div>
      <div class="text-gray-500 dark:text-gray-200 pb-1">
        <ColorModeSwitch class="hover:text-gray-700 dark:hover:text-gray-300 px-5" />
      </div>
    </div>
  </div>
</template>
