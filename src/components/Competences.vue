<script setup>
import { ref } from 'vue'

const competences = [
    'python',
    'vue',
    'c',
    'php',
    'sql',
    'jquery',
    'phpmyadmin',
]
</script>

<template>
    <div class="bg-slate-950 text-slate-50">
        <h1 class="text-4xl text-center py-20">Competences</h1>
        <div class="flex justify-center items-center">
            <ul class="max-w-xl grid grid-cols-6 grid-rows-3 gap-10">
                <li class="" v-for="competence in competences" :key="competence"><img :src="`src/assets/logo_${competence}.png`" :alt="`${competence} logo`"></li>
            </ul>
        </div>
    </div>
</template>