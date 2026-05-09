<script setup>
import { ref, onMounted } from "vue";

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

  const section = document.querySelector("#journey");

  if (section) {
    observer.observe(section);
  }
});
</script>
<template>
  <section
    id="journey"
    class="relative min-h-screen flex items-center justify-center px-6 md:px-16 py-[120px]"
  >
    <img
      src="/public/images/pattern2.webp"
      alt=""
      class="w-20 md:w-28 absolute right-2 md:right-10 top-5 md:top-10 spin opacity-80"
    />

    <div
     :class="show ? 'opacity-100 translate-y-0' : 'opacity-0 translate-y-20'"
      class="w-full max-w-4xl bg-gray-50 border-4 border-gray-800 rounded-3xl p-8 md:p-10 shadow-[10px_10px_0px_gray] transition-all duration-700 ease-out"
    >
      <!-- LABEL -->
      <p
        class="inline-block bg-gray-900 rounded-2xl text-white px-4 py-2 font-black mb-6"
      >
        MY JOURNEY
      </p>

      <!-- TITLE -->
      <h1 class="text-4xl md:text-6xl font-black leading-tight mb-10">
        Learning Journey <br />
        & Skill Development
      </h1>

      <!-- TIMELINE -->
      <div class="relative border-l-4 border-gray-800 ml-4 md:ml-8">
        <!-- ITEM 1 -->
        <div class="mb-10 ml-6 relative">
          <span
            class="absolute -left-[14px] top-2 w-6 h-6 bg-yellow-300 border-4 border-gray-800 rounded-full shadow-[4px_4px_0px_gray]"
          ></span>
          <div
            class="bg-yellow-200 border-4 border-gray-800 p-5 rounded-2xl shadow-[6px_6px_0px_gray]"
          >
            <h3 class="text-xl font-black">Bachelor of Computer Science</h3>
            <p class="text-sm font-bold text-gray-700">2023 - 2027</p>
            <p class="mt-2 font-bold text-gray-800">
              Ain Shams University, Faculty of Computers and Information Science.<br>
              My time at FCIS, provided a rigorous foundation in systems engineering, complex algorithms, and scalable software architecture.
            </p>
          </div>
        </div>

        <!-- ITEM 2 -->
        <div class="mb-10 ml-6 relative">
          <span
            class="absolute -left-[14px] top-2 w-6 h-6 bg-green-300 border-4 border-gray-800 rounded-full shadow-[4px_4px_0px_gray]"
          ></span>
          <div
            class="bg-green-200 border-4 border-gray-800 p-5 rounded-2xl shadow-[6px_6px_0px_gray]"
          >
            <h3 class="text-xl font-black">Hello, World: Learning to Speak Code</h3>
            <p class="text-sm font-bold text-gray-700">2023</p>
            <p class="mt-2 font-bold text-gray-800">
              Where it all started. Before web frameworks and scalable architectures, I dove into the core of computer science.
              Mastering fundamental programming logic, data structures, and the problem-solving mindset that powers my code today.
            </p>
          </div>
        </div>

        <!-- ITEM 3 -->
        <div class="mb-10 ml-6 relative">
          <span
            class="absolute -left-[14px] top-2 w-6 h-6 bg-blue-300 border-4 border-gray-800 rounded-full shadow-[4px_4px_0px_gray]"
          ></span>
          <div
            class="bg-blue-200 border-4 border-gray-800 p-5 rounded-2xl shadow-[6px_6px_0px_gray]"
          >
            <h3 class="text-xl font-black">MAM Summer training in Frontend Development</h3>
            <p class="text-sm font-bold text-gray-700">2024</p>
            <p class="mt-2 font-bold text-gray-800">
             I wrote my first lines of HTML and CSS <br>
             Completed MAM certification program, gaining a comprehensive understanding of Web fundamentals, Frontend end, and Web applications.<br>
             The course covered programming for Web development, Frontend tools, including Bootstrap.
            </p>
          </div>
        </div>

        <!-- ITEM 4 -->
        <div class="mb-10 ml-6 relative">
          <span
            class="absolute -left-[14px] top-2 w-6 h-6 bg-pink-300 border-4 border-gray-800 rounded-full shadow-[4px_4px_0px_gray]"
          ></span>
          <div
            class="bg-pink-200 border-4 border-gray-800 p-5 rounded-2xl shadow-[6px_6px_0px_gray]"
          >
            <h3 class="text-xl font-black">.NET Full Stack Diploma - DEPI</h3>
            <p class="text-sm font-bold text-gray-700">2025</p>
            <p class="mt-2 font-bold text-gray-800">
              a professional .NET Full Stack diploma at DEPI, covering both frontend and backend development with modern frameworks and tools.
              The program focuses on building scalable and secure web applications using ASP.NET Core, C#, and SQL for the backend,
              while mastering modern frontend practices for responsive and interactive user interfaces.
            </p>
          </div>
        </div>

        <!-- ITEM 5 -->
        <!-- <div class="ml-6 relative">
          <span
            class="absolute -left-[14px] top-2 w-6 h-6 bg-yellow-300 border-4 border-gray-800 rounded-full shadow-[4px_4px_0px_gray]"
          ></span>
          <div
            class="bg-yellow-200 border-4 border-gray-800 p-5 rounded-2xl shadow-[6px_6px_0px_gray]"
          >
            <h3 class="text-xl font-black">Fresh Graduate</h3>
            <p class="text-sm font-bold text-gray-700">2027</p>
            <p class="mt-2 font-bold text-gray-800">
            
            </p>
          </div>
        </div> -->
      </div>
    </div>
    <img
      src="/public/images/pattern1.webp"
      alt=""
      class="w-20 md:w-28 absolute left-2 md:left-10 bottom-5 md:bottom-10 spin opacity-80"
    />
  </section>
</template>
