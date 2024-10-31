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
  <div class="mb-24 bg-slate-950 text-slate-50">
    <h1 class="flex justify-center py-20 text-center text-4xl">Competences</h1>
    <div class="flex items-center justify-center">
      <ul class="grid lg:grid-cols-7 gap-2 md:gap-2 grid-cols-4">
        <li
          class="justitfy-center flex items-center"
          v-for="competence in competences"
          :key="competence"
        >
          <div class="group flex flex-col items-center gap-3">
            <div class="flex h-14 w-14 items-center justify-center">
              <img
                class="object-cover"
                :src="`/logo_${competence}.png`"
                :alt="`${competence} logo`"
              />
            </div>
            <p
              class="text-center text-sm text-slate-400 transition group-hover:text-emerald-400 cursor-default"
            >
              {{ competence }}
            </p>
          </div>
        </li>
      </ul>
    </div>
  </div>
</template>
