<script setup>
import Contact from "./Contact.vue";
import ThreeCanvas from "./ThreeCanvas.vue";
</script>

<template>
  <div class="w-full gap-5 bg-slate-950 px-20 sm:px-40 lg:px-80 pt-40 text-slate-50 flex">
    <div>
      <h1 class="text-6xl">
        <span
        class="bg-gradient-to-r from-emerald-400 via-emerald-300 to-cyan-400 bg-clip-text text-transparent"
        >Alfred de Vulpian</span
        >
      </h1>
      <h3 class="pt-3 text-2xl">Etudiant en école d'ingénieur</h3>
      <p class="text-md w-full lg:w-4/5 pt-3 leading-8 text-slate-300">
        Je me spécialise en <span class="border-b border-cyan-400">Python</span>
        dans l'objectif de m'orienter vers la
        <span class="border-b border-cyan-400">Data Science</span> et
        <span class="border-b border-cyan-400">l'intelligence artificielle</span>.
      </p>
      <Contact />
    </div>
    <ThreeCanvas />
  </div>
</template>
