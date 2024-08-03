<script setup>
import { ref } from 'vue'
import ParcoursElement from './ParcoursElement.vue'

const parcours = ref([
    {
        periode: '2022 - 2027',
        statut: 'en_cours',
        diplome: "Préparation d'un diplome d'ingénieur en informatique",
        etablissement: 'ECE Paris - Paris 15'
    },
    {
        periode: 'Sep 2024 - Dec 2024',
        statut: 'en_cours',
        diplome: 'Computer Science',
        etablissement: 'Baruch College - New York, Manhattan'
    },
    {
        periode: '2022',
        statut: 'check',
        diplome: 'Baccalauréat mention bien - Options Mathématiques & NSI',
        etablissement: 'Lycée Saint Erembert - Saint Germain en Laye'
    },
    {
        periode: '2020',
        statut: 'check',
        diplome: "Brevet d'Initiation à l'Aéronautique",
        etablissement: 'Lycée Saint Erembert - Saint Germain en Laye'
    }
])
</script>

<template>
    <div class="bg-slate-950 text-slate-50">
        <h1 class="text-4xl text-center py-20">Parcours</h1>
        <div class="flex justify-start flex-col items-center">
            <ul>
                <ParcoursElement
                v-for="element in parcours"
                :key="element.periode"
                :periode="element.periode"
                :statut="element.statut"
                :diplome="element.diplome"
                :etablissement="element.etablissement" />
            </ul>
        </div>
    </div>
</template>