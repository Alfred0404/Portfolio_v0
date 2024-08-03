<script setup>
import { onMounted, ref } from "vue";

const props = defineProps(["periode", "statut", "diplome", "etablissement"]);
const elementRef = ref(null);

onMounted(() => {
  const parent = elementRef.value.parentElement;
  const children = parent.children;
  if (children[children.length - 1] === elementRef.value) {
    elementRef.value
      .querySelector("div")
      .style.setProperty("--after-display", "none");
  }
});
</script>

<template>
  <div ref="elementRef" class="bg-slate-950 text-slate-50">
    <div
      class="group relative flex cursor-pointer flex-col items-start py-10 ps-10 text-slate-400 after:absolute after:left-[8px] after:top-20 after:z-10 after:h-36 after:w-0.5 after:bg-slate-900"
      :style="{ '--after-display': 'block' }"
    >
      <p
        class="relative text-xl font-bold text-slate-50 transition group-hover:text-emerald-400"
      >
        {{ props.periode }}
      </p>
      <p class="mt-4 transition group-hover:text-emerald-500">
        {{ props.diplome }}
      </p>
      <p class="mb-4 mt-1 transition group-hover:text-emerald-500">
        {{ props.etablissement }}
      </p>
      <div
        class="absolute -left-1 h-6 w-6 rounded-full bg-slate-600"
        v-if="props.statut === 'check'"
      ></div>
      <img
        class="absolute -left-1 h-7 w-7"
        v-if="props.statut === 'en_cours'"
        src="../assets/en_cours.svg"
        alt=""
      />
    </div>
  </div>
</template>

<style scoped>
div::after {
  display: var(--after-display);
}
</style>
