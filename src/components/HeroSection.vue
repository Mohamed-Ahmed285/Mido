<script setup>
import { ref, onMounted } from "vue";
import { Github, Mail, Linkedin } from "lucide-vue-next";

const show = ref(false);

onMounted(() => {
  const observer = new IntersectionObserver(
    ([entry]) => {
      if (entry.isIntersecting) {
        show.value = true;
      }
    },
    {
      threshold: 0.2,
    },
  );

  const section = document.querySelector("#home");

  if (section) {
    observer.observe(section);
  }
});

const downloadCV = () => {
  const link = document.createElement("a");
  link.href = `${import.meta.env.BASE_URL}cv/MohamedAbdelghaniResume.pdf`;
  link.download = "MohamedAbdelghaniResume.pdf";
  link.click();
};

</script>
<template>
  <section
    id="home"
    :class="show ? 'opacity-100 translate-y-0' : 'opacity-0 translate-y-20'"
    class="min-h-screen flex items-center justify-center px-2 sm:px-6 md:px-16 py-22 transition-all duration-700 ease-out">
    <div class="max-w-7xl w-full grid md:grid-cols-2 gap-12 items-center">
      <!-- TEXT -->
      <div class="rounded-3xl p-8 md:p-12">
        <p
          class="inline-block bg-gray-900 text-white px-4 py-2 rounded-xl text-sm md:text-base font-black mb-6"
        >
          FULL-STACK ENTHUSIAST
        </p>

        <h1
          class="text-5xl md:text-6xl font-black text-black leading-tight mb-2"
        >
          HI! I'M
          <span class="text-orange-500">Mohamed AbdelGhani</span>
        </h1>

        <p class="text-lg md:text-1xl font-bold text-black mb-8">
          I am a Third-year Student at Faculty of Computers and Information Science Ainshams University, passionate about creating beautiful web experiences.
        </p>

        <div
          class="flex flex-row flex-wrap md:justify-start gap-4 w-full mb-4"
        >
          <!-- BUTTON PROJECT -->
          <a
            href="#projects"
            class="bg-white border-4 border-gray-900 px-5 md:px-6 py-3 font-black text-sm md:text-base shadow-[5px_5px_0px_gray] hover:translate-x-1 hover:translate-y-1 hover:shadow-none transition duration-200"
          >
            My Projects
          </a>

          <!-- BUTTON CONTACT -->
          <button
            @click="downloadCV"
            class="bg-orange-500 text-white border-4 border-gray-900 px-5 md:px-6 py-3 font-black text-sm md:text-base shadow-[5px_5px_0px_gray] hover:translate-x-1 hover:translate-y-1 hover:shadow-none transition duration-200"
          >
            Download CV
          </button>
        </div>

        <!-- SOCIAL -->
          <div class="flex gap-4 flex-wrap flex flex-row flex-wrap md:justify-start gap-4">
            <!-- GITHUB -->
            <a
              href="https://github.com/Mohamed-Ahmed285"
              target="_blank"
              class="bg-orange-500 border-4 border-gray-800 md:px-2.5 py-2.5 text-white shadow-[4px_4px_0px_gray] hover:translate-x-1 hover:translate-y-1 hover:shadow-none transition duration-200"
            >
              <Github :size="20" />
            </a>

            <!-- Email -->
            <a
              href="#contact"
              class="bg-white border-4 border-gray-800 md:px-2.5 py-2.5 shadow-[4px_4px_0px_gray] hover:translate-x-1 hover:translate-y-1 hover:shadow-none transition duration-200"
            >
              <Mail :size="20" />
            </a>

            <!-- LINKEDIN -->
            <a
              href="https://www.linkedin.com/in/mohamed-ahmed-3034872aa/"
              target="_blank"
              class="bg-blue-500 text-white border-4 border-gray-800 md:px-2.5 py-2.5 shadow-[4px_4px_0px_gray] hover:translate-x-1 hover:translate-y-1 hover:shadow-none transition duration-200"
            >
              <Linkedin :size="20" />
            </a>
          </div>
    
      </div>

      <!-- IMAGE -->
      <div class="hidden md:flex justify-center">
        <div
          class="bg-orange-500 border-4 border-gray-900 rounded-2xl p-2 shadow-[10px_10px_0px_gray] -rotate-2 floating"
        >
          <img
            src="/public/images/1775652667771.jpeg"
            alt="profile"
            class="w-[280px] md:w-[310px] rounded-2xl border-4 border-black object-cover"
          />
        </div>
      </div>
    </div>
  </section>
</template>
