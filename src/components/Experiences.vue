<script setup>
import { ref } from 'vue'
import ExperienceElement from './ExperienceElement.vue'

const experiences = ref([
    {
        periode: 'Jan 2024 - Jan 2024',
        status: 'check',
        experience: 'Stage - Data Scientist',
        entreprise: 'Havas DBi'
    }
])
</script>

<template>
    <div class="bg-slate-950 text-slate-50">
        <h1 class="text-4xl text-center py-20">Experiences</h1>
        <div class="flex justify-start flex-col items-center">
            <ul class="flex justify-center flex-col">
                <ExperienceElement v-for="element in experiences" :key="element.periode" :periode="element.periode" :status="element.status" :experience="element.experience" :entreprise="element.entreprise" />
            </ul>
        </div>
    </div>
</template>