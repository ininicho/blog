<script lang="ts">
export default {
  data () {
    return {
      navItems: [
        {
          name: 'Home',
          route: '/'
        },
        {
          name: 'Stories',
          route: '/stories'
        }
        // {
        //   name: 'About',
        //   route: '/about'
        // }
      ],
      collapseMenu: true,
      menuIcon: 'heroicons-outline:menu'
    }
  },
  computed: {
    showCollapseMenu () {
      return this.collapseMenu ? 'hidden' : 'visible'
    }
  },
  methods: {
    isCurrentPage (path) {
      return this.$route.path === path
    },
    handleCollapseMenu () {
      if (this.collapseMenu) {
        this.menuIcon = 'heroicons-outline:x'
      } else {
        this.menuIcon = 'heroicons-outline:menu'
      }
      this.collapseMenu = !this.collapseMenu
      this.$emit('collapse-menu', this.collapseMenu)
    }
  }
}
</script>

<template>
  <div>
    <div class="flex flex-row justify-center px-16 pt-12 pb-6">
      <div class="container flex flex-wrap justify-between items-center">
        <NuxtLink to="/" class="flex justify-start items-center ml-0">
          <Icon name="carbon:cafe" class="w-10 h-10 text-xl font-bold text-gray-700 dark:text-gray-300" />
        </NuxtLink>
        <div class="flex justify-end items-center md:order-2 text-gray-500 dark:text-gray-200">
          <ColorModeSwitch class="hover:text-gray-700 dark:hover:text-gray-300 px-5" />
          <button
            type="button"
            class="inline-flex items-center rounded-lg md:hidden hover:text-gray-700 dark:hover:text-gray-300"
            @click="handleCollapseMenu"
          >
            <Icon :name="menuIcon" />
          </button>
        </div>
      </div>
    </div>
    <div :class="showCollapseMenu" class="flex fixed justify-center w-screen h-screen backdrop-opacity-20 bg-gray-50 dark:bg-gray-900">
      <ul class="flex flex-col translate-y-10 place-items-center items-center font-bold text-gray-500 dark:text-gray-200 text-5xl">
        <li v-for="(navItem, index) in navItems" :key="index" class="py-3">
          <NuxtLink :to="navItem.route" class="block py-2">
            {{ navItem.name }}
          </NuxtLink>
        </li>
      </ul>
    </div>
  </div>
</template>
