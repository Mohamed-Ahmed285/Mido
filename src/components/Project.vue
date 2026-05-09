<script setup>
import { ref, onMounted } from "vue";

import project1 from "../assets/images/project1.png";
import project2 from "../assets/images/project2.png";
import project3 from "../assets/images/project3.png";
import project4 from "../assets/images/project4.png";
import project5 from "../assets/images/project5.png";
import project6 from "../assets/images/project6.png";
import project7 from "../assets/images/project7.png";

import cert1 from "../assets/images/cert1.jpg";
import cert2 from "../assets/images/cert2.png";
import cert3 from "../assets/images/cert3.png";
import cert4 from "../assets/images/cert4.jpg";
import cert5 from "../assets/images/cert5.jpg";

const activeTab = ref("projects");

const projects = [
  {
    title: "A Personal Website for IAC - Insight Accounting & Consultant ",
    desc: "A business website for IAC (Insight Accounting & Consultant) to showcase accounting and consulting services with a clean, modern, and user-friendly design.",
    image: project2,
    tech: [
      { name: "Nodejs", class: "bg-green-300" },
      { name: "React", class: "bg-blue-300" },
      { name: "NextJS", class: "bg-yellow-300" },
      { name: "Tailwind", class: "bg-purple-300" },
    ],
  },
  {
    title: "Thoth Gate",
    desc: "Online Learning Centre A modern e-learning platform that blends ancient wisdom with modern education.",
    image: project3,
    tech: [
      { name: "HTML", class: "bg-green-300" },
      { name: "CSS", class: "bg-purple-300" },
      { name: "JS", class: "bg-yellow-300" },
      { name: "Laravel", class: "bg-blue-300" },
      { name: "MySQL", class: "bg-pink-300" },
    ],
  },
   {
    title: "Faculty of Nursing - Innovation University Website",
    desc: "Non-profit resource hub for Innovation University Faculty of Nursing students — textbooks, course materials, and campus location guides by academic level.",
    image: project1,
    tech: [
      { name: "HTML", class: "bg-green-300" },
      { name: "CSS", class: "bg-blue-300" },
      { name: "JS", class: "bg-yellow-300" },
      { name: "Tailwind", class: "bg-pink-300" },
    ],
  },
   {
    title: "Shelf",
    desc: "A full-stack web application for managing personal libraries and tracking reading progress. Designed with a focus on clean architecture and intuitive user discovery.",
    image: project4,
    tech: [
      { name: "React", class: "bg-blue-300" },
      { name: "Nodejs", class: "bg-yellow-300" },
      { name: "MongoDB", class: "bg-green-300" },
      { name: "Express", class: "bg-gray-300" },
    ],
  },
   {
    title: "SkyLine",
    desc: "A JavaFX-based flight reservation system — book flights, manage passengers, and view schedules with a modern GUI.",
    image: project5,
    tech: [
      { name: "Java", class: "bg-green-300" },
      { name: "CSS", class: "bg-blue-300" },
      { name: "Java-fx", class: "bg-yellow-300" },
      { name: "Json", class: "bg-pink-300" },
    ],
  },
   {
    title: "Pac-Man",
    desc: "A classic Pac-Man clone built in C++ with SFML — tile-based maps, ghost AI, and arcade-style gameplay.",
    image: project6,
    tech: [
      { name: "CPP", class: "bg-green-300" },
      { name: "SFML", class: "bg-blue-300" },
      { name: "AI players", class: "bg-red-300" },
    ],
  },
];

const certificates = [
  {
    image: cert1,
  },
  {
    image: cert2,
  },
  {
    image: cert3,
  },
  {
    image: cert4,
  },
  {
    image: cert5,
  },
];
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

  const section = document.querySelector("#projects");

  if (section) {
    observer.observe(section);
  }
});
</script>
<template>
  <section
    id="projects"
    :class="show ? 'opacity-100 translate-y-0' : 'opacity-0 translate-y-20'"
    class="relative min-h-screen px-6 md:px-16 py-[130px] transition-all duration-700 ease-out"
  >
    <!-- TITLE -->
    <img
      src="/public/images/pattern3.webp"
      alt=""
      class="absolute top-30 right-5 md:right-16 w-28 md:w-40 float opacity-60 pointer-events-none"
    />

    <div class="max-w-7xl mx-auto mb-14">
      <p
        class="inline-block bg-orange-500 text-white px-4 py-2 font-black rounded-2xl mb-5"
      >
        MY PROJECTS
      </p>

      <h1 class="text-4xl md:text-6xl font-black leading-tight mb-4">
        Selected Projects
      </h1>

      <p class="font-bold text-gray-700 text-lg max-w-2xl">
        Some of the projects I've created use React, NextJs, .Net, and Tailwind CSS with modern and responsive designs.
      </p>
      <!-- TAB BUTTON -->
      <div class="flex flex-wrap gap-2 md:gap-4 mt-8">
        <button
          @click="activeTab = 'projects'"
          :class="
            activeTab === 'projects'
              ? 'bg-orange-500 text-white'
              : 'bg-white text-black'
          "
          class="border-4 border-gray-800 px-3 py-1.5 text-sm md:px-5 md:py-2 md:text-base rounded-2xl font-black shadow-[4px_4px_0px_gray] transition duration-200"
        >
          Projects
        </button>

        <button
          @click="activeTab = 'certificates'"
          :class="
            activeTab === 'certificates'
              ? 'bg-orange-500 text-white'
              : 'bg-white text-black'
          "
          class="border-4 border-gray-800 px-3 py-1.5 text-sm md:px-5 md:py-2 md:text-base rounded-2xl font-black shadow-[4px_4px_0px_gray] transition duration-200"
        >
          Certificates
        </button>

        <button
          @click="activeTab = 'skills'"
          :class="
            activeTab === 'skills'
              ? 'bg-orange-500 text-white'
              : 'bg-white text-black'
          "
          class="border-4 border-gray-800 px-3 py-1.5 text-sm md:px-5 md:py-2 md:text-base rounded-2xl font-black shadow-[4px_4px_0px_gray] transition duration-200"
        >
          Skills
        </button>
      </div>
    </div>

    <!-- PROJECT LIST -->
    <div class="max-w-7xl mx-auto">
      <Transition name="pop" mode="out-in">
        <div :key="activeTab">
          <!-- Proj -->
          <div
            v-if="activeTab === 'projects'"
            class="max-w-7xl mx-auto grid md:grid-cols-2 lg:grid-cols-3 gap-7">
            <div
              v-for="(project, index) in projects"
              :key="index"
              class="bg-gray-50 border-4 border-gray-800 rounded-2xl overflow-hidden shadow-[10px_10px_0px_gray] hover:-translate-y-2 transition duration-300"
            >
              <!-- IMAGE -->
              <img
                :src="project.image"
                alt="project"
                class="w-full h-[220px] object-cover border-b-4 border-gray-800"
              />

              <!-- CONTENT -->
              <div class="p-6">
                <div class="flex flex-wrap gap-3 mb-5">
                  <span
                    v-for="(tech, i) in project.tech"
                    :key="i"
                    :class="tech.class"
                    class="border-2 border-gray-800 px-3 py-1 font-black text-sm"
                  >
                    {{ tech.name }}
                  </span>
                </div>

                <h2 class="text-2xl font-black mb-3">{{ project.title }}</h2>

                <p class="font-bold text-gray-700 mb-6">
                  {{ project.desc }}
                </p>
              </div>
            </div>
          </div>

          <!-- CERTIFICATES -->
          <div
            v-else-if="activeTab === 'certificates'"
            class="max-w-7xl mx-auto grid md:grid-cols-2 lg:grid-cols-3 gap-4">
            <div
              v-for="(cert, index) in certificates"
              :key="index"
              class="bg-gray-50 border-4 border-gray-800 rounded-2xl overflow-hidden"
            >
              <!-- IMAGE -->
              <img
                :src="cert.image"
                alt="certificate"
                class="w-full h-[280px] object-cover border-b-4 border-gray-800"
              />
            </div>
          </div>

          <!-- Skills -->
          <div
            v-else="activeTab === 'skills'"
            class="max-w-7xl mx-auto grid grid-cols-2 md:grid-cols-3 lg:grid-cols-4 gap-6">
            <!-- HTML -->
            <div
              class="bg-gray-100 border-4 border-gray-800 rounded-3xl p-6 shadow-[8px_8px_0px_gray] flex flex-col items-center justify-center hover:-translate-y-2 transition duration-300"
            >
              <img
                src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/html5/html5-original.svg"
                class="w-16 h-16 mb-4"
              />
              <p class="font-black text-lg">HTML</p>
            </div>

            <!-- CSS -->
            <div
              class="bg-gray-100 border-4 border-gray-800 rounded-3xl p-6 shadow-[8px_8px_0px_gray] flex flex-col items-center justify-center hover:-translate-y-2 transition duration-300"
            >
              <img
                src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/css3/css3-original.svg"
                class="w-16 h-16 mb-4"
              />
              <p class="font-black text-lg">CSS</p>
            </div>

            <div
              class="bg-gray-100 border-4 border-gray-800 rounded-3xl p-6 shadow-[8px_8px_0px_gray] flex flex-col items-center justify-center hover:-translate-y-2 transition duration-300"
            >
              <img
                src="https://devicon-website.vercel.app/api/javascript/original.svg"
                class="w-16 h-16 mb-4"
              />
              <p class="font-black text-lg">JS</p>
            </div>

           
            <div
              class="bg-gray-100 border-4 border-gray-800 rounded-3xl p-6 shadow-[8px_8px_0px_gray] flex flex-col items-center justify-center hover:-translate-y-2 transition duration-300"
            >
              <img
                src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/react/react-original.svg"
                class="w-16 h-16 mb-4"
              />
              <p class="font-black text-lg">React JS</p>
            </div>
            <div
              class="bg-gray-100 border-4 border-gray-800 rounded-3xl p-6 shadow-[8px_8px_0px_gray] flex flex-col items-center justify-center hover:-translate-y-2 transition duration-300"
            >
              <img
                src="https://devicon-website.vercel.app/api/nodejs/original-wordmark.svg"
                class="w-16 h-16 mb-4"
              />
              <p class="font-black text-lg">Nodejs</p>
            </div>

            <!-- TAILWIND -->
            <div
              class="bg-gray-100 border-4 border-gray-800 rounded-3xl p-6 shadow-[8px_8px_0px_gray] flex flex-col items-center justify-center hover:-translate-y-2 transition duration-300"
            >
              <img
                src="https://www.vectorlogo.zone/logos/tailwindcss/tailwindcss-icon.svg"
                class="w-16 h-16 mb-4"
              />
              <p class="font-black text-lg">Tailwind</p>
            </div>

            <div
              class="bg-gray-100 border-4 border-gray-800 rounded-3xl p-6 shadow-[8px_8px_0px_gray] flex flex-col items-center justify-center hover:-translate-y-2 transition duration-300"
            >
              <img
                src="https://devicon-website.vercel.app/api/csharp/original.svg"
                class="w-16 h-16 mb-4"
              />
              <p class="font-black text-lg">C#</p>
            </div>
            <div
              class="bg-gray-100 border-4 border-gray-800 rounded-3xl p-6 shadow-[8px_8px_0px_gray] flex flex-col items-center justify-center hover:-translate-y-2 transition duration-300"
            >
              <img
                src="https://devicon-website.vercel.app/api/dot-net/original.svg"
                class="w-16 h-16 mb-4"
              />
              <p class="font-black text-lg">.Net</p>
            </div>

            <!-- BOOTSTRAP -->
            <div
              class="bg-gray-100 border-4 border-gray-800 rounded-3xl p-6 shadow-[8px_8px_0px_gray] flex flex-col items-center justify-center hover:-translate-y-2 transition duration-300"
            >
              <img
                src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/bootstrap/bootstrap-original.svg"
                class="w-16 h-16 mb-4"
              />
              <p class="font-black text-lg">Bootstrap</p>
            </div>


            <div
              class="bg-gray-100 border-4 border-gray-800 rounded-3xl p-6 shadow-[8px_8px_0px_gray] flex flex-col items-center justify-center hover:-translate-y-2 transition duration-300">
              <img
                src="https://devicon-website.vercel.app/api/mongodb/original.svg"
                class="w-16 h-16 mb-4"
              />
              <p class="font-black text-lg">MongoDB</p>
            </div>
            <div
              class="bg-gray-100 border-4 border-gray-800 rounded-3xl p-6 shadow-[8px_8px_0px_gray] flex flex-col items-center justify-center hover:-translate-y-2 transition duration-300">
              <img
                src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/microsoftsqlserver/microsoftsqlserver-original.svg"
                class="w-16 h-16 mb-4"
              />
              <p class="font-black text-lg">Sql Server</p>
            </div>
                <div
              class="bg-gray-100 border-4 border-gray-800 rounded-3xl p-6 shadow-[8px_8px_0px_gray] flex flex-col items-center justify-center hover:-translate-y-2 transition duration-300"
            >
              <img
                src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/github/github-original.svg"
                class="w-16 h-16 mb-4"
              />
              <p class="font-black text-lg">Github</p>
            </div>

          </div>
        </div>
      </Transition>
    </div>
  </section>
</template>
