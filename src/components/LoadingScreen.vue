<template>
  <div
    class="fixed inset-0 z-[9999] bg-orange-500 flex items-center justify-center"
  >
    <div class="text-center">
      <!-- Spinner -->
      <div
        class="w-16 h-16 border-4 border-white border-t-transparent rounded-full animate-spin mx-auto"
      ></div>

      <!-- Text -->
      <p class="text-white mt-6 text-lg tracking-widest">
        LOADING...
      </p>
    </div>
  </div>
</template>