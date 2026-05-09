<script setup>
import { ref, onMounted } from "vue";

import Navbar from "./components/Navbar.vue";
import HeroSection from "./components/HeroSection.vue";
import About from "./components/About.vue";
import Projects from "./components/Project.vue";
import Journey from "./components/Journey.vue";
import Contact from "./components/Contact.vue";
import Footer from "./components/Footer.vue";
import ClickSpark from "./components/ClickSpark.vue";
import LoadingScreen from "./components/LoadingScreen.vue";

const isLoading = ref(true);

onMounted(() => {
  setTimeout(() => {
    isLoading.value = false;
  }, 3000); 
});
</script>

<template>
  <!-- Loading -->
  <LoadingScreen v-if="isLoading" />

  <!-- Main Content -->
  <ClickSpark
    v-else
    spark-color="#ff6b6b"
    :spark-size="12"
    :spark-radius="25"
    :spark-count="12"
    :duration="600"
    easing="ease-out"
    :extra-scale="1.2"
  >
    <div class="grid-bg min-h-screen">
      <Navbar />
      <HeroSection />
      <About />
      <Projects />
      <Journey />
      <Contact />
      <Footer/>
    </div>
  </ClickSpark>
</template>