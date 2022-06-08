<template>
  <div class=".layout-styled container mx-auto">
    <NavigationBar />
    <slot />
    <FooterSection />
  </div>
</template>

<style lang="postcss">
.layout-styled {
    @apply relative transition duration-75 ease-in-out;
}
</style>
