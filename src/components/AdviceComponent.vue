<script lang="ts">
export default {
  data() {
    return {
      adviceNumber: 117,
      adviceText:
        "It is easy to sit up and take notice, what's difficult is getting up and taking action."
    }
  },
  methods: {
    async writeAdvice() {
      try {
        fetch('https://api.adviceslip.com/advice')
          .then((response) => response.json())
          .then((data) => {
            console.log(data)
            this.adviceNumber = data.slip.id
            this.adviceText = data.slip.advice
          })
      } catch (e) {
        console.error(e)
      }
    }
  }
}
</script>

<template>
  <main
    id="advice"
    class="relative inline-block text-center rounded-2xl p-10 max-w-lg bg-[var(--color-background-advice)]"
  >
    <div class="uppercase text-sm tracking-widest text-[var(--color-text-number)]">
      Advice #{{ adviceNumber }}
    </div>
    <h1 class="text-2xl text-[var(--color-text-advice)] my-8 mx-0">{{ adviceText }}</h1>
    <div class="mb-5">
      <svg
        class="mx-auto"
        xmlns="http://www.w3.org/2000/svg"
        width="1.5rem"
        height="1.5rem"
        viewBox="0 0 16 16"
      >
        <path
          fill="white"
          d="M7 7v7H0V6.9c0-4.8 4.5-5.4 4.5-5.4l.6 1.4s-2 .3-2.4 1.9C2.3 6 3.1 7 3.1 7H7zm9 0v7H9V6.9c0-4.8 4.5-5.4 4.5-5.4l.6 1.4s-2 .3-2.4 1.9c-.4 1.2.4 2.2.4 2.2H16z"
        />
      </svg>
    </div>
    <button
      class="flex justify-center items-center h-20 w-20 rounded-full bg-[var(--color-button-background)] absolute top-full left-1/2 cursor-pointer -translate-x-1/2 -translate-y-1/2 border-none transition delay-200 hover:shadow-[0_0_20px_var(--shadow-c-green)]"
      v-on:click="writeAdvice()"
    >
      <svg xmlns="http://www.w3.org/2000/svg" height="2Rem" viewBox="0 0 640 512">
        <path
          d="M274.9 34.3c-28.1-28.1-73.7-28.1-101.8 0L34.3 173.1c-28.1 28.1-28.1 73.7 0 101.8L173.1 413.7c28.1 28.1 73.7 28.1 101.8 0L413.7 274.9c28.1-28.1 28.1-73.7 0-101.8L274.9 34.3zM200 224a24 24 0 1 1 48 0 24 24 0 1 1 -48 0zM96 200a24 24 0 1 1 0 48 24 24 0 1 1 0-48zM224 376a24 24 0 1 1 0-48 24 24 0 1 1 0 48zM352 200a24 24 0 1 1 0 48 24 24 0 1 1 0-48zM224 120a24 24 0 1 1 0-48 24 24 0 1 1 0 48zm96 328c0 35.3 28.7 64 64 64H576c35.3 0 64-28.7 64-64V256c0-35.3-28.7-64-64-64H461.7c11.6 36 3.1 77-25.4 105.5L320 413.8V448zM480 328a24 24 0 1 1 0 48 24 24 0 1 1 0-48z"
        />
      </svg>
    </button>
  </main>
</template>

<style>
@media (max-width: 578px) {
  #advice {
    width: 100%;
    margin: 20px;
  }
}
</style>
