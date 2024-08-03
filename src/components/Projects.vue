<script setup>
import Project from "./Project.vue";
import { ref } from "vue";

const projects = ref([
  {
    name: "Sportify",
    tag_name: "School project",
    description:
      "Sportify est un projet réalisé dans le cadre de mes études consistant en une application web de mise en relation entre client et coach sportif spécialisés dans de nombreuses disciplines.",
    stack: ["html", "css", "js", "jquery", "php", "sql", "phpmyadmin"],
    image_path: "src/assets/sportify.png",
    link: "https://github.com/Alfred0404/Projet_Web_Dynamique_Sportify",
  },
  {
    name: "Rocket League Esport Tracker",
    tag_name: "Personnal project",
    description:
      "Rocket League Esport Tracker est une application web permettant de récupérer des informations sur des matchs d'e-sport Rocket League, passé ou à venir, grâce à l'API octane.gg.",
    stack: ["vue", "nodejs"],
    image_path: "src/assets/rl_esport.png",
    link: "https://github.com/Alfred0404/rocket-esport-vue",
  },
  {
    name: "ECE-World",
    tag_name: "School project",
    description:
      "ECE-World est un projet réalisé dans le cadre de mes études consistant en un jeu top-down 2D contenant plusieurs mini-jeux (guitar hero, labyrinthe, etc).",
    stack: ["c", "allegro"],
    image_path: "src/assets/eceworld.png",
    link: "https://github.com/Alfred0404/ece-world-paris-ing1-2022-2023-nintendeau",
  },
]);
</script>

<template>
  <div
    class="mb-44 flex flex-col items-center justify-center bg-slate-950 text-slate-50"
  >
    <h1 class="py-20 text-center text-4xl">Mes projets</h1>
    <div class="mx-48 flex flex-wrap justify-center gap-10 py-10">
      <Project
        v-for="project in projects"
        :key="project.name"
        :name="project.name"
        :tag_name="project.tag_name"
        :description="project.description"
        :stack="project.stack"
        :image_path="project.image_path"
        :link="project.link"
      />
    </div>
    <a
      class="mx-10 mb-10 w-fit rounded-lg border border-solid border-slate-600 p-4 px-10 font-bold text-slate-50 transition hover:cursor-pointer hover:border-slate-400 hover:bg-slate-900"
      href="https://github.com/Alfred0404?tab=repositories"
      target="_blank"
      >Tous mes projets</a
    >
  </div>
</template>
