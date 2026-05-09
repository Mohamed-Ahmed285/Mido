<script setup>
import { ref, onMounted } from 'vue'

const showContact = ref(false)

onMounted(() => {
  const observer = new IntersectionObserver(
    ([entry]) => {
      if (entry.isIntersecting) {
        showContact.value = true
      }
    },
    {
      threshold: 0.2,
    }
  )

  const section = document.querySelector('#contact')

  if (section) {
    observer.observe(section)
  }
})
</script>
<template>
  <section
    id="contact"
    class="min-h-screen relative px-6 md:px-16 py-[130px] flex items-center"
  >
    <img
      src="/public/images/pattern4.webp"
      alt=""
      class="w-40 md:w-40 absolute -right-1 md:-right-1 top-5 md:top-2 opacity-80"
    />
    <div
     :class="
    showContact
      ? 'opacity-100 translate-x-0'
      : 'opacity-0 -translate-x-20'"
      class="max-w-7xl mx-auto w-full grid md:grid-cols-2 gap-12 items-center transition-all duration-700 ease-out"
    >
      <!-- LEFT CONTENT -->
      <div>
        <p
          class="inline-block bg-gray-900 text-white px-4 py-2 rounded-2xl font-black mb-5"
        >
          CONTACT ME
        </p>

        <h1 class="text-4xl md:text-6xl font-black leading-tight mb-6">
          Let’s Build <br />
          Something Awesome
        </h1>

        <p class="font-bold text-gray-700 text-lg leading-relaxed mb-8">
          Have a project, idea, or collaboration? Please contact me using the form below.
        </p>

        <!-- CONTACT INFO -->
        <div class="flex flex-col gap-5">
          <div
            class="bg-gray-50 border-4 border-gray-800 p-5 rounded-2xl shadow-[6px_6px_0px_gray]"
          >
            <p class="font-black text-xl mb-1">Email</p>

            <p class="font-bold text-gray-700">mohamed.ahmed.abdelghani6@gmail.com</p>
          </div>

          <div
            class="bg-yellow-300 border-4 border-gray-800 p-5 rounded-2xl shadow-[6px_6px_0px_gray]"
          >
            <p class="font-black text-xl mb-1">Location</p>

            <p class="font-bold text-gray-700">Egypt</p>
          </div>
        </div>
      </div>

      <!-- RIGHT FORM -->
      <div
        class="bg-gray-50 border-4 border-gray-800 rounded-3xl p-8 md:p-10 shadow-[10px_10px_0px_gray]"
      >
        <form class="flex flex-col gap-6">
          <!-- NAME -->
          <div>
            <label class="block font-black mb-2"> Your Name </label>

            <input
              type="text"
              placeholder="Enter your name"
              class="w-full border-4 border-gray-800 bg-gray-100 px-5 py-4 rounded-xl font-bold outline-none focus:bg-white"
            />
          </div>

          <!-- EMAIL -->
          <div>
            <label class="block font-black mb-2"> Your Email </label>

            <input
              type="email"
              placeholder="Enter your email"
              class="w-full border-4 border-gray-800 bg-gray-100 px-5 py-4 rounded-xl font-bold outline-none focus:bg-white"
            />
          </div>

          <!-- MESSAGE -->
          <div>
            <label class="block font-black mb-2"> Message </label>

            <textarea
              rows="5"
              placeholder="Write your message..."
              class="w-full border-4 border-gray-800 bg-gray-100 px-5 py-4 rounded-xl font-bold outline-none resize-none focus:bg-white"
            ></textarea>
          </div>

          <!-- BUTTON -->
          <button
            type="submit"
            class="bg-orange-500 text-white border-4 border-gray-800 px-6 py-4 font-black shadow-[6px_6px_0px_gray] hover:translate-x-1 hover:translate-y-1 hover:shadow-none transition duration-200"
          >
            Send Message
          </button>
        </form>
      </div>
    </div>
  </section>
</template>
