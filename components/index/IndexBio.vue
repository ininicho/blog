<script setup lang="ts">
import biocard from '@/static/biocard-1.jpg'
</script>

<template>
  <div class="flex flex-col md:flex-row justify-between md:pt-7 text-gray-500 dark:text-gray-200">
    <div class="flex flex-col my-4 md:basis-3/5 md:pr-28 md:text-2xl md:py-10">
      <!-- <ContentRenderer :value="bioCardContent" unwrap="p" /> -->
      <span class="py-4 text-4xl font-semibold">Hello World!</span>
      <br>
      <span class="py-2 text-justify">
        I'm currently a third year student studying Computer Science at the University of Waterloo. 
        Currently in an internship at FarmLink Marketing Solutions, working as a software 
        developer.  
      </span>
      <span class="py-2 text-justify">
        I specialize in fullstack web development. I love learning new web frameworks and languages, 
        and I'm always looking to improve my skills. I'm also a big fan of the open-source community,
        and I'm always looking forward to learn new things.  
      </span>
      <span class="py-2 text-justify">
        I write about my journey as a developer and many other things.
      </span>
    </div>
    <div class="flex py-auto md:basis-2/5 md:pr-7">
      <img :src="biocard" alt="Cover" class="object-cover object-center rounded-3xl">
    </div>
  </div>
</template>
