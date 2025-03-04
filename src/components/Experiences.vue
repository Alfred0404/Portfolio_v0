<script setup>
import { ref } from "vue";
import ExperienceElement from "./ExperienceElement.vue";

const experiences = ref([
  {
    periode: "2024 - 2025",
    status: "en_cours",
    contrat: "",
    experience: "Vice président Création",
    entreprise: "Network Gaming Association",
    competences: ["leadership", "team working", "canva", "design", "communication"]
  },
  {
    periode: "Jan 2025 - Jan 2025",
    status: "check",
    contrat: "Stage",
    experience: "Stagiaire Data Scientist",
    entreprise: "Crédit Agricole Assurances",
    competences: ["annotation", "pandas", "python"]
  },
  {
    periode: "Jan 2024 - Jan 2024",
    status: "check",
    contrat: "Stage",
    experience: "Stagiaire Data Scientist",
    entreprise: "Havas DBi",
    competences: [
      "python",
      "sql",
      "data science",
      "teamwork",
      "pandas",
      "numpy",
    ]
  },
  {
    periode: "2023 - 2024",
    status: "check",
    contrat: "",
    experience: "Responsable Création",
    entreprise: "Network Gaming Association",
    competences: ["team working", "canva", "design", "communication"]
  },
  {
    periode: "2023",
    status: "check",
    contrat: "Bénévole",
    experience: "Aide aux devoirs",
    entreprise: "AFEV",
    competences: ["bénévolat", "pédagogie"]
  },
  {
    periode: "2012 - 2022",
    status: "check",
    contrat: "",
    experience: "Scoutisme",
    entreprise: "Troupe 1ère Mesnil-Le-Roi",
    competences: ["leadership", "team working", "bénévolat", "communication"]
  }
]);
</script>

<template>
  <div class="mx-20 md:mx-0 bg-slate-950 text-slate-50 mb-44">
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
