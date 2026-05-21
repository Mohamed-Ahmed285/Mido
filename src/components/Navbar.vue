<script setup>
import { ref } from "vue";

const isOpen = ref(false);
const refreshPage = () => {
  window.location.reload();
};
</script>

<template>
  <nav
    class="fixed top-0 left-0 w-full bg-gray-100 border-b-4 border-gray-800 p-3 z-50 px-6 md:px-10"
  >
    <div class="flex justify-between items-center">
      <!-- LOGO -->
       <div class="flex gap-1 items-center justify-between" >    
          <img
            src="../../public/images/logo.png"
            @click="refreshPage"
            class="cursor-pointer w-14 h-8 drop-shadow-lg hover:translate-x-1 hover:translate-y-1 hover:drop-shadow-none transition duration-200"/>
          <!-- <h1 class="text-2xl font-black">
            Mido
          </h1> -->
      </div>
    

      <!-- DESKTOP MENU -->
      <div class="hidden md:flex items-center gap-8">
        <div class="flex gap-6 font-bold text-lg">
          <a
            href="#home"
            class="relative group hover:text-orange-500 transition"
          >
            Home

            <span
              class="absolute left-0 -bottom-1 w-0 h-[3px] bg-orange-500 transition-all duration-300 group-hover:w-full"
            ></span>
          </a>

          <a
            href="#about"
            class="relative group hover:text-orange-500 transition"
          >
            About

            <span
              class="absolute left-0 -bottom-1 w-0 h-[3px] bg-orange-500 transition-all duration-300 group-hover:w-full"
            ></span>
          </a>

          <a
            href="#projects"
            class="relative group hover:text-orange-500 transition"
          >
            Projects

            <span
              class="absolute left-0 -bottom-1 w-0 h-[3px] bg-orange-500 transition-all duration-300 group-hover:w-full"
            ></span>
          </a>

          <a
            href="#journey"
            class="relative group hover:text-orange-500 transition"
          >
            Journey

            <span
              class="absolute left-0 -bottom-1 w-0 h-[3px] bg-orange-500 transition-all duration-300 group-hover:w-full"
            ></span>
          </a>

          <a
            href="#contact"
            class="relative group hover:text-orange-500 transition"
          >
            Contact

            <span
              class="absolute left-0 -bottom-1 w-0 h-[3px] bg-orange-500 transition-all duration-300 group-hover:w-full"
            ></span>
          </a>
        </div>

        <!-- BUTTON -->
        <a
          href="#contact"
          class="bg-orange-500 border-4 text-white border-gray-800 px-5 py-2 font-black shadow-[4px_4px_0px_gray] hover:translate-x-1 hover:translate-y-1 hover:shadow-none transition duration-200"
        >
          Let's Talk
        </a>
      </div>

      <!-- MOBILE BUTTON -->
      <button
        @click="isOpen = !isOpen"
        class="md:hidden bg-orange-500 border-4 border-gray-800 px-3 py-2 font-black shadow-[4px_4px_0px_gray]"
      >
        ☰
      </button>
    </div>

    <!-- MOBILE MENU -->
    <div
      v-if="isOpen"
      class="md:hidden mt-5 bg-white border-4 border-gray-800 p-5 rounded-2xl"
    >
      <div class="flex flex-col gap-5 font-bold text-lg">
        <a
          href="#home"
          @click="isOpen = false"
          class="hover:text-orange-500 transition"
        >
          Home
        </a>

        <a
          href="#about"
          @click="isOpen = false"
          class="hover:text-orange-500 transition"
        >
          About
        </a>

        <a
          href="#projects"
          @click="isOpen = false"
          class="hover:text-orange-500 transition"
        >
          Projects
        </a>

        <a
          href="#journey"
          @click="isOpen = false"
          class="hover:text-orange-500 transition"
        >
          Journey
        </a>

        <a
          href="#contact"
          @click="isOpen = false"
          class="hover:text-orange-500 transition"
        >
          Contact
        </a>

        <a
          href="#contact"
          @click="isOpen = false"
          class="bg-orange-500 text-white border-4 border-gray-800 px-5 py-3 font-black text-center shadow-[4px_4px_0px_gray]"
        >
          Let's Talk
        </a>
      </div>
    </div>
  </nav>
</template>
