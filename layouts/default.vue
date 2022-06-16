<template>
  <div :class="showCollapseMenu" class=".layout-styled container mx-auto">
    <TheNavbar @collapseMenu="handleCollapseMenu" />
    <slot />
    <TheFooter />
  </div>
</template>

<script lang="ts">
export default {
  data () {
    return {
      collapseMenu: true
    }
  },
  computed: {
    showCollapseMenu () {
      return this.collapseMenu ? '' : 'h-screen overflow-y-hidden'
    }
  },
  methods: {
    handleCollapseMenu (currentState) {
      this.collapseMenu = currentState
    }
  }
}
</script>

<style lang="postcss">
.layout-styled {
    @apply relative transition duration-75 ease-in-out;
}
</style>
