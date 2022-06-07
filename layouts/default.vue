<template>
    <Html lang="en" />
    <Head>
        <title>Some Title</title>
    </Head>
    <Meta property="og:image" content="/cover.jpg" />
    <Meta name="twitter:card" content="summary_large_image" />
    <div class="max-w-full px-8 py-8">
        <Navbar />
        <slot />
    </div>
    <Footer />
</template>