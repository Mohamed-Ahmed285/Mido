<script setup>
import { ref, onMounted } from 'vue'
import emailjs from '@emailjs/browser'

const showContact = ref(false)
const formRef = ref(null)
const isSubmitting = ref(false)
const statusMessage = ref('')

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

const sendEmail = async () => {
  isSubmitting.value = true
  statusMessage.value = ''

  try {
    await emailjs.sendForm(
      import.meta.env.VITE_EMAILJS_SERVICE_ID, 
      import.meta.env.VITE_EMAILJS_TEMPLATE_ID, 
      formRef.value, 
      import.meta.env.VITE_EMAILJS_PUBLIC_KEY
    )
    
    statusMessage.value = 'Message sent successfully! I will get back to you soon.'
    formRef.value.reset() // Clears the form inputs
    setTimeout(() => {
      statusMessage.value = ''
    }, 5000)

  } catch (error) {
    console.error('FAILED...', error.text)
    statusMessage.value = 'Oops! Something went wrong. Please try again.'
    setTimeout(() => {
      statusMessage.value = ''
    }, 5000)
  } finally {
    isSubmitting.value = false
  }
}
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
        <form ref="formRef" @submit.prevent="sendEmail" class="flex flex-col gap-6">
          <!-- NAME -->
          <div>
            <label class="block font-black mb-2"> Your Name </label>

            <input
              type="text"
              name="user_name"
              required
              placeholder="Enter your name"
              class="w-full border-4 border-gray-800 bg-gray-100 px-5 py-4 rounded-xl font-bold outline-none focus:bg-white"
            />
          </div>

          <!-- EMAIL -->
          <div>
            <label class="block font-black mb-2"> Your Email </label>
            <input
              type="email"
              name="user_email"
              required
              placeholder="Enter your email"
              class="w-full border-4 border-gray-800 bg-gray-100 px-5 py-4 rounded-xl font-bold outline-none focus:bg-white"
            />
          </div>

          <!-- MESSAGE -->
          <div>
            <label class="block font-black mb-2"> Message </label>

            <textarea
              name="message"
              required
              rows="5"
              placeholder="Write your message..."
              class="w-full border-4 border-gray-800 bg-gray-100 px-5 py-4 rounded-xl font-bold outline-none resize-none focus:bg-white"
            ></textarea>
          </div>

          <!-- BUTTON -->
          <button
            type="submit"
            :disabled="isSubmitting"
            :class="isSubmitting ? 'opacity-70 cursor-not-allowed' : 'hover:translate-x-1 hover:translate-y-1 hover:shadow-none'"
            class="bg-orange-500 text-white border-4 border-gray-800 px-6 py-4 font-black shadow-[6px_6px_0px_gray] transition duration-200"
          >
            {{ isSubmitting ? 'Sending...' : 'Send Message' }}
          </button>


          <transition name="fade">
            <div 
              v-if="statusMessage" 
              class="flex items-center justify-center gap-2 mt-4 transition-all duration-300"
            >
              <svg class="w-5 h-5 -rotate-90" viewBox="0 0 20 20">
                <circle 
                  cx="10" cy="10" r="8" 
                  fill="none" 
                  class="stroke-gray-300" 
                  stroke-width="3" 
                />
                <circle
                  cx="10" cy="10" r="8"
                  fill="none"
                  stroke-width="3"
                  stroke-linecap="round"
                  class="animate-countdown"
                  :class="statusMessage.includes('wrong') ? 'stroke-red-600' : 'stroke-green-600'"
                />
              </svg>

          <p v-if="statusMessage" class="font-bold text-center mt-2" :class="statusMessage.includes('wrong') ? 'text-red-600' : 'text-green-600'">
            {{ statusMessage }}
          </p>

          </div>
          </transition>

        </form>
      </div>
    </div>
  </section>
</template>
