<template>
  <div class="grid grid-cols-1 md:grid-cols-2 pt-6 pb-12 px-16 md:mx-12 items-start text-gray-700 dark:text-gray-200">
    <div class="basis-1/2 flex-col px-6 py-6">
      <div>
        <p class="text-4xl font-semibold">
          Lets work together
        </p>
      </div>
      <div class="w-3/4 my-10">
        <p class="text-xl">
          Lorem ipsum dolor sit amet, consectetur adipiscing elit. Lorem ipsum dolor sit amet, consectetur adipiscing elit.
        </p>
      </div>
      <div class="flex flex-wrap">
        <a href="/"><Icon name="mdi:twitter" class="mr-3" /></a>
        <a href="/"><Icon name="mdi:instagram" class="mx-3" /></a>
        <a href="/"><Icon name="ic:outline-discord" class="mx-3" /></a>
        <a href="/"><Icon name="mdi:linkedin" class="mx-3" /></a>
      </div>
    </div>
    <div class="basis-1/2 mb-24">
      <div class="flex-col items-center text-gray-900">
        <input id="name" type="text" name="name" class="block w-3/4 outline-none px-6 py-4 my-5 md:text-md bg-gray-700 dark:bg-gray-200 text-gray-700" placeholder="Name">
        <input id="email" type="text" name="email" class="block w-3/4 outline-none px-6 py-4 my-5 md:text-md bg-gray-700 dark:bg-gray-200 text-gray-700" placeholder="Email">
        <textarea id="message" name="message" class="block w-3/4 h-48 resize-none outline-none px-6 py-6 my-5 md:text-md bg-gray-700 dark:bg-gray-200 text-gray-700" placeholder="Type your message here" />
      </div>
      <button class="block w-1/3 bg-gray-500 text-gray-200 py-5">
        Submit
      </button>
    </div>
  </div>
</template>
