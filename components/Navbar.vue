<script lang="ts">
export default {
  data() {
    return {
      navItems: [
        {
          name: 'Stories',
          route: '/',
        },
        {
          name: 'About',
          route: '/about',
        },
      ],
    }
  },
  methods: {
    isCurrentPage(path) {
      return this.$route.path === path;
    }
  }
}
</script>

<template>
  <nav class="flex flex-row justify-center px-16 pt-12 pb-6">
    <div class="container flex flex-wrap justify-between items-center">
      <NuxtLink to="/" class="flex justify-start items-center ml-0">
        <p class="text-xl font-bold text-gray-800 dark:text-gray-200">NS</p>
      </NuxtLink>
      <div class="flex justify-end items-center md:order-2 text-gray-500 dark:text-gray-200">
        <ColorModeSwitch class="hover:text-gray-700 dark:hover:text-gray-300 px-5" />
        <!-- TODO: Fix Menu Collapse Button -->
        <button data-collapse-toggle="mobile-menu" type="button" class="inline-flex items-center rounded-lg md:hidden hover:text-gray-700 dark:hover:text-gray-300" aria-controls="mobile-menu" aria-expanded="false">
          <Icon name="heroicons-outline:menu" />
        </button>
      </div>
      <div class="hidden justify-end items-center w-full md:flex md:w-auto md:grow md:order-1" id="mobile-menu">
        <ul class="flex flex-col mt-4 items-end md:flex-row md:space-x-8 md:mt-0 md:text-md md:font-medium text-gray-500 dark:text-gray-200">
          <li>
            <NuxtLink to="/" class="font-bold block py-2 pr-4 pl-3">Stories</NuxtLink>
          </li>
          <li>
            <NuxtLink to="/about" class="block py-2 pr-4 pl-3">About</NuxtLink>
          </li>
        </ul>
      </div>
    </div>
  </nav>
</template>
