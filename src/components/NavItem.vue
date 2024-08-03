<script setup>
import { defineProps } from "vue";

const props = defineProps(["name"]);

const HandlescrollToElement = () => {
  console.log("scrolling to ", props.name);
  element.scrollIntoView({ behavior: "smooth" });
};
</script>

<template>
  <button
    @click="HandlescrollToElement"
    class="rounded-lg bg-slate-50 p-2 px-6 text-slate-950 transition hover:cursor-pointer hover:bg-emerald-400"
  >
    {{ $props.name }}
  </button>
</template>
