<template>
  <div class="grid grid-cols-1 md:grid-cols-2 py-6 md:pb-12 px-5 lg:px-16 lg:mx-12 items-start text-gray-700 dark:text-gray-200">
    <div class="lg:basis-1/2 flex-col px-6 py-6">
      <div>
        <p class="text-4xl font-semibold">
          Lets work together
        </p>
      </div>
      <div class="md:w-3/4 my-10">
        <p class="text-xl">
          If you are interested in anything me-related or just wanting to reach out, let me know by sending me a message! Take it sleazy!
        </p>
      </div>
      <div class="flex flex-wrap">
        <a href="https://twitter.com/ininicho_"><Icon name="mdi:twitter" class="mr-3" /></a>
        <a href="https://instagram.com/ininicho_"><Icon name="mdi:instagram" class="mx-3" /></a>
        <a href="https://open.spotify.com/user/nicho101002"><Icon name="mdi:spotify" class="mx-3" /></a>
        <a href="https://www.linkedin.com/in/nicholaus-suprapto-73abb8190/"><Icon name="mdi:linkedin" class="mx-3" /></a>
      </div>
    </div>
    <div class="md:basis-1/2 mb-24 md:mx-6 px-6 flex-col items-start text-gray-900">
      <input 
        v-model="name"
        type="text" 
        placeholder="Name"
        class="block w-full outline-none px-6 py-4 my-5 md:text-md bg-gray-700 dark:bg-gray-200 text-gray-700" 
      />
      <input 
        v-model="email"
        type="text" 
        placeholder="Email"
        class="block w-full outline-none px-6 py-4 my-5 md:text-md bg-gray-700 dark:bg-gray-200 text-gray-700" 
      />
      <textarea 
        v-model="message"
        placeholder="Type your message here"
        class="block w-full h-48 resize-none outline-none px-6 py-6 my-5 md:text-md bg-gray-700 dark:bg-gray-200 text-gray-700" 
      />
      <button 
        class="block w-1/3 bg-gray-500 text-gray-200 py-5"
        @click="handleSubmit"
      >
        Submit
      </button>
    </div>
  </div>
</template>

<script lang="ts">
export default ({
  data() {
    return {
      name: '',
      email: '',
      message: '',
    }
  },
  methods: {
    resetForm() {
      this.name = '';
      this.email = '';
      this.message = '';
    },
    handleSubmit() {
      const emailSubject = 'subject=' + encodeURIComponent("Hey it's " + this.name + ' - ' + this.email);
      const emailMesssage = 'body=' + encodeURIComponent(this.message);
      const emailLink = 'mailto:nsuprapt@uwaterloo.ca?' + [emailSubject, emailMesssage].join('&');
      window.open(emailLink);
      this.resetForm();
    }
  }
})
</script>

