<script lang="ts">
const works = [
  {
    id: 1,
    show: true,
    title: 'FarmLink Marketing Solutions',
    description: 'A marketing solution for farms',
    image: '/assets/diner.jpg',
    text: `I'm currently a third year student studying Computer Science at the University of Waterloo. I'm also currently in an internship at FarmLink Marketing Solutions, working as a software developer.
I specialize in fullstack web development. I love to learn new frameworks and languages, and I'm always looking to improve my skills. I'm also a big fan of the open-source community, and I'm always looking to learn new things.
I write about my journey as a developer and many other things.`
  },
  {
    id: 2,
    show: true,
    title: 'Paramount Commerce',
    description: 'A company that provides payment solution for online gaming',
    image: '/assets/station.jpg',
    text: `I'm currently a third year student studying Computer Science at the University of Waterloo. I'm also currently in an internship at FarmLink Marketing Solutions, working as a software developer.
I specialize in fullstack web development. I love to learn new frameworks and languages, and I'm always looking to improve my skills. I'm also a big fan of the open-source community, and I'm always looking to learn new things.
I write about my journey as a developer and many other things.`
  },
  {
    id: 2,
    show: true,
    title: 'University of Waterloo',
    description: 'A company that provides payment solution for online gaming',
    image: '/assets/einstein.jpg',
    text: `I'm currently a third year student studying Computer Science at the University of Waterloo. I'm also currently in an internship at FarmLink Marketing Solutions, working as a software developer.
I specialize in fullstack web development. I love to learn new frameworks and languages, and I'm always looking to improve my skills. I'm also a big fan of the open-source community, and I'm always looking to learn new things.
I write about my journey as a developer and many other things.`
  }
]

export default {
  data () {
    return {
      works
    }
  }
}
</script>

<template>
  <div class="block flex-col flex-wrap py-7 items-center text-gray-700 dark:text-gray-200">
    <div class="flex">
      <p class="text-4xl pl-5 font-semibold">
        Experiences
      </p>
    </div>
    <div class="grid grid-cols-2 py-10">
      <WorksItem
        v-for="(work, index) in works"
        :key="index"
        :work="work"
      />
    </div>
  </div>
</template>
