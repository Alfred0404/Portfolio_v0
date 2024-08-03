<script setup>
import { ref } from "vue";
import ParcoursElement from "./ParcoursElement.vue";

const parcours = ref([
  {
    periode: "2022 - 2027",
    statut: "en_cours",
    diplome: "Préparation d'un diplome d'ingénieur en informatique",
    etablissement: "ECE Paris - Paris 15",
  },
  {
    periode: "Sep 2024 - Dec 2024",
    statut: "en_cours",
    diplome: "Computer Science Major",
    etablissement: "Baruch College - New York, Manhattan",
  },
  {
    periode: "2022",
    statut: "check",
    diplome: "Baccalauréat mention bien - Options Mathématiques & NSI",
    etablissement: "Lycée Saint Erembert - Saint Germain en Laye",
  },
  {
    periode: "2020",
    statut: "check",
    diplome: "Brevet d'Initiation à l'Aéronautique",
    etablissement: "Lycée Saint Erembert - Saint Germain en Laye",
  },
]);
</script>

<template>
  <div class="mb-44 mx-28 md:mx-0 bg-slate-950 text-slate-50">
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
        />
      </ul>
    </div>
  </div>
</template>
