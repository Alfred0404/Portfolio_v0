<script setup>
import { ref } from "vue";
import ExperienceElement from "./ExperienceElement.vue";

const experiences = ref([
  {
    periode: "Jan 2024 - Jan 2024",
    status: "check",
    contrat: "Stage",
    experience: "Data Scientist",
    entreprise: "Havas DBi",
    competences: [
      "python",
      "sql",
      "data science",
      "teamwork",
      "pandas",
      "numpy",
    ],
  },
  {
    periode: "Since Oct 2023",
    status: "check",
    contrat: "Stage",
    experience: "Vice-président Création",
    entreprise: "Association NGA - ECE Paris",
    competences: ["teamwork", "leadership", "Communication", "organisation"],
  },
]);
</script>

<template>
  <div class="mx-20 mb-44 bg-slate-950 text-slate-50 md:mx-0">
    <h1 class="py-20 text-center text-4xl">Experiences</h1>
    <div class="flex flex-col items-center justify-start">
      <ul class="flex w-fit flex-col justify-center">
        <ExperienceElement
          v-for="element in experiences"
          :key="element.periode"
          :periode="element.periode"
          :status="element.status"
          :experience="element.experience"
          :entreprise="element.entreprise"
          :competences="element.competences"
          :contrat="element.contrat"
        />
      </ul>
    </div>
  </div>
</template>
