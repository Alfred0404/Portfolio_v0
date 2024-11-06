<script setup>
import Header from "./components/Header.vue";
import HeroBanner from "./components/HeroBanner.vue";
import Projects from "./components/Projects.vue";
import Parcours from "./components/Parcours.vue";
import Experiences from "./components/Experiences.vue";
import Competences from "./components/Competences.vue";
import Footer from "./components/Footer.vue";
</script>

<template>
  <div class="bg-slate-950 w-full">
    <Header/>
    <HeroBanner />
    <Competences />
    <Projects />
    <Parcours />
    <Experiences />
    <Footer />
  </div>
</template>
