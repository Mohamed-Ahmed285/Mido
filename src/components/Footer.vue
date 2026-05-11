<script setup>
import { Github, Instagram, Linkedin } from "lucide-vue-next";
</script>
<template>
  <footer
    class="border-t-4 border-gray-800 bg-gray-100 px-6 md:px-10 py-6 mt-20"
  >
    <div class="max-w-7xl mx-auto grid md:grid-cols-3 gap-12 pt-3">
      <!-- LEFT -->
      <div>
        <h1 class="text-3xl font-black mb-4">Mido</h1>

        <p class="font-bold text-gray-700 leading-relaxed max-w-sm text-1xl">
        Web enthusiast focused on building modern, responsive, 
        and interactive websites.
        </p>
      </div>

      <!-- MENU -->
      <div>
        <h2 class="text-2xl font-black mb-5">Navigation</h2>

        <div class="flex flex-col gap-4 font-black text-lg">
          <a href="#home" class="hover:text-orange-500 transition"> Home </a>

          <a href="#about" class="hover:text-orange-500 transition"> About </a>

          <a href="#projects" class="hover:text-orange-500 transition">
            Projects
          </a>

          <a href="#contact" class="hover:text-orange-500 transition">
            Contact
          </a>
        </div>
      </div>

      <!-- SOCIAL -->
      <div>
        <h2 class="text-2xl font-black mb-5">Social Media</h2>

        <div>
          <div class="flex gap-4 flex-wrap">
            <!-- GITHUB -->
            <a
              href="https://github.com/Mohamed-Ahmed285"
              target="_blank"
              class="bg-orange-500 border-4 border-gray-800 p-4 text-white shadow-[4px_4px_0px_gray] hover:translate-x-1 hover:translate-y-1 hover:shadow-none transition duration-200"
            >
              <Github :size="28" />
            </a>

            <!-- Instgram -->
            <a
              href="https://www.instagram.com/mido_o316/"
              target="_blank"
              class="bg-white border-4 border-gray-800 p-4 shadow-[4px_4px_0px_gray] hover:translate-x-1 hover:translate-y-1 hover:shadow-none transition duration-200"
            >
              <Instagram :size="28" />
            </a>

            <!-- LINKEDIN -->
            <a
              href="https://www.linkedin.com/in/mohamed-ahmed-3034872aa/"
              target="_blank"
              class="bg-blue-500 text-white border-4 border-gray-800 p-4 shadow-[4px_4px_0px_gray] hover:translate-x-1 hover:translate-y-1 hover:shadow-none transition duration-200"
            >
              <Linkedin :size="28" />
            </a>
          </div>
        </div>
      </div>
    </div>

    <!-- BOTTOM -->
    <div
      class="border-t-4 border-dashed border-gray-400 mt-8 pt-6 text-center font-bold text-gray-600"
    >
      © 2026 Mohamed AbdelGhani — All Rights Reserved
    </div>
  </footer>
</template>
