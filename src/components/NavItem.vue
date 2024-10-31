<script setup>
const props = defineProps(["name"]);

const HandlescrollToElement = () => {
  const element_parser = {
    "A propos de moi": 700,
    Projets: 1460,
    Parcours: 2500,
    Experiences: 3650,
    Compétences: 4800,
  };

  const element_height = element_parser[props.name];
  window.scrollTo({
    top: element_height,
    behavior: "smooth",
  });
};
</script>

<template>
  <button
    @click="HandlescrollToElement"
    class="text-md rounded-lg p-2 px-6 text-sm text-slate-50 transition hover:cursor-pointer hover:text-emerald-400"
  >
    {{ $props.name }}
  </button>
</template>
