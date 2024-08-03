<script setup>
import { onMounted, ref } from 'vue';

const props = defineProps(['periode', 'statut', 'diplome', 'etablissement']);
const elementRef = ref(null);

onMounted(() => {
    const parent = elementRef.value.parentElement;
    const children = parent.children;
    if (children[children.length - 1] === elementRef.value) {
        elementRef.value.querySelector('div').style.setProperty('--after-display', 'none');
    }
});
</script>

<template>
    <div ref="elementRef" class="bg-slate-950 text-slate-50">
        <div class="group cursor-pointer text-slate-400 flex flex-col items-start ps-10 py-10 relative
                    after:absolute after:z-10 after:w-0.5 after:h-36 after:bg-slate-900 after:left-[8px] after:top-20"
             :style="{ '--after-display': 'block' }">

            <p class="text-xl relative font-bold text-slate-50 group-hover:text-emerald-400 transition">{{ props.periode }}</p>
            <p class="mt-4 group-hover:text-emerald-500 transition">{{ props.diplome }}</p>
            <p class="mt-1 mb-4 group-hover:text-emerald-500 transition">{{ props.etablissement }}</p>
            <div class="absolute -left-1 w-6 h-6 bg-slate-600 rounded-full" v-if="props.statut === 'check'"></div>
            <img class="absolute -left-1 w-7 h-7" v-if="props.statut === 'en_cours'" src="../assets/en_cours.svg" alt="">
        </div>
    </div>
</template>

<style scoped>
div::after {
    display: var(--after-display);
}
</style>