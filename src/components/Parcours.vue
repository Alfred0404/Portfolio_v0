<script setup>
import { ref } from "vue";
import ParcoursElement from "./ParcoursElement.vue";

const parcours = ref([
  {
    periode: "2022 - 2027",
    statut: "en_cours",
    diplome: "Préparation d'un diplome d'ingénieur en informatique",
    etablissement: "ECE Paris - Paris 15",
    courses: ["mathématiques", "éléctronique", "c", "python", "développement web"],
  },
  {
    periode: "Sep 2024 - Dec 2024",
    statut: "check",
    diplome: "Computer Science Major",
    etablissement: "Baruch College - New York, Manhattan",
    courses: ["python", "machine learning", "éléctronique", "robotique"],
  },
  {
    periode: "2022",
    statut: "check",
    diplome: "Baccalauréat mention bien - Options Mathématiques & NSI",
    etablissement: "Lycée Saint Erembert - Saint Germain en Laye",
    courses: ["mathématiques", "numérique et sciences de l'informatique", "python"],
  },
  {
    periode: "2020",
    statut: "check",
    diplome: "Brevet d'Initiation à l'Aéronautique",
    etablissement: "Lycée Saint Erembert - Saint Germain en Laye",
    courses : [],
  },
]);
</script>

<template>
  <div class="mb-24 mx-20 md:mx-0 bg-slate-950 text-slate-50">
    <h1 class="py-20 text-center text-4xl">Parcours</h1>
    <div class="flex flex-col items-center justify-start">
      <ul>
        <ParcoursElement
          v-for="element in parcours"
          :key="element.periode"
          :periode="element.periode"
          :statut="element.statut"
          :diplome="element.diplome"
          :etablissement="element.etablissement"
          :courses="element.courses"
        />
      </ul>
    </div>
  </div>
</template>
