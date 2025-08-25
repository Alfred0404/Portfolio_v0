<script setup>
import Project from "./Project.vue";
import { ref } from "vue";

const projects = ref([
  {
    name: "GAN - Generative Adversarial Network",
    tag_name: "Personnal project",
    description:
      "Implémentation d'un GAN (Generative Adversarial Network) pour la génération d'images à partir de bruit aléatoire, en utilisant PyTorch.",
    stack: ["python"],
    image_path: "/gan.png",
    link: "https://github.com/Alfred0404/gan",
  },
  {
    name: "Sportify",
    tag_name: "School project",
    description:
      "Sportify est un projet réalisé dans le cadre de mes études consistant en une application web de mise en relation entre client et coach sportif spécialisés dans de nombreuses disciplines.",
    stack: ["html", "css", "js", "jquery", "php", "sql", "phpmyadmin"],
    image_path: "/sportify.png",
    link: "https://github.com/Alfred0404/Projet_Web_Dynamique_Sportify",
  },
  {
    name: "Genetic AI Racer",
    tag_name: "School project",
    description:
      "Implémentation d'un algorithme génétique pour l'entrainement d'agents autonomes sur un jeu de course, grâce à un réseau de neurones et d'un systme de récompenses.",
    stack: ["python"],
    image_path: "/genetic_ai_racer.png",
    link: "https://github.com/Alfred0404/genetic_ai_racer",
  }
]);

const current_project = ref([
  {
    name: "HunterShip",
    tag_name: "Personnal project",
    description:
      "Projet visant à accompagner la recherche d'emploi en automatisant certaines tâches comme la recherche d'offres, la gestion des candidatures et l'envoi d'emails.",
    stack: ["python"],
    image_path: "/huntership.png",
    link: "https://github.com/Alfred0404/huntership",
  }
]);
</script>

<template>
  <div
    class="mb-24 flex flex-col items-center justify-center bg-slate-950 text-slate-50"
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
    <h1 class="text-center text-3xl mt-8">En cours</h1>
    <div class="mx-48 flex flex-wrap justify-center gap-10 py-10">
      <Project
        v-for="project in current_project"
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
      class="mx-10 mb-10 w-fit rounded-lg border border-solid border-slate-600 p-4 px-10 text-sm font-bold text-slate-50 transition hover:cursor-pointer hover:border-slate-400 hover:bg-slate-900"
      href="https://github.com/Alfred0404?tab=repositories"
      target="_blank"
      >Tous mes projets</a
    >
  </div>
</template>
