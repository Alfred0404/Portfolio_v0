<script setup>
import { onMounted, ref } from 'vue';

const props = defineProps(['periode', 'status', 'experience', 'entreprise']);
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
        <div class="text-slate-400 flex flex-col items-start ps-10 py-10 relative
                    after:absolute after:z-10 after:w-0.5 after:h-36 after:bg-slate-900 after:left-[8px] after:top-20"
             :style="{ '--after-display': 'block' }">

            <p class="text-xl relative font-bold text-slate-50">{{ props.periode }}</p>
            <p class="mt-4">{{ props.experience }}</p>
            <p class="mt-1 mb-4">{{ props.entreprise }}</p>
            <div class="absolute -left-1 w-6 h-6 bg-slate-600 rounded-full" v-if="props.status === 'check'"></div>
            <img class="absolute -left-1 w-7 h-7" v-if="props.status === 'en_cours'" src="../assets/en_cours.svg" alt="">
        </div>
    </div>
</template>

<style scoped>
div::after {
    display: var(--after-display);
}
</style>