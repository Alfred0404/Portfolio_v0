<script setup>
import { ref } from "vue";

const competences = [
  "python",
  "vue",
  "c",
  "php",
  "sql",
  "jquery",
  "phpmyadmin",
];
</script>

<template>
  <div class="bg-slate-950 text-slate-50 mb-44">
    <h1 class="py-20 text-center text-4xl">Competences</h1>
    <div class="flex items-center justify-center">
      <ul class="grid max-w-xl grid-cols-5 grid-rows-3 gap-10">
        <li
          class="justitfy-center flex items-center p-2"
          v-for="competence in competences"
          :key="competence"
        >
          <img
            :src="`src/assets/logo_${competence}.png`"
            :alt="`${competence} logo`"
          />
        </li>
      </ul>
    </div>
  </div>
</template>
