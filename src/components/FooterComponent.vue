<template>
  <footer
    class="flex items-center justify-center font-mono font-bold p-5 bg-[#252627] text-[#a9a9b3] min-w-full bottom-0 fixed left-0"
  >
    <a href="https://peerlist.io/adhiraj" target="_blank">
      <span class="mr-1">></span>
      <span class="text-lg">_ bytehead</span>
      <span class="cursor"></span>
    </a>
  </footer>
</template>

<style>
.cursor {
  display: inline-block;
  width: 10px;
  height: 1rem;
  background: #fe5186;
  margin-left: 5px;
  border-radius: 1px;
  animation: blink 1s infinite;
}

@keyframes blink {
  0% {
    opacity: 0;
  }
  50% {
    opacity: 1;
  }
  100% {
    opacity: 0;
  }
}
</style>
