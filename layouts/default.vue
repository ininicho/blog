<template>
    <div class=".layout-styled">
        <Navbar />
        <slot />
        <Footer />
    </div>
</template>

<style lang="postcss">
.layout-styled {
    @apply relative transition duration-75 ease-in-out;
}
</style>