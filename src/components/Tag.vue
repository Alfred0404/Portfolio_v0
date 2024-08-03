<script setup>
import { defineProps } from "vue";

const props = defineProps(["tag_name"]);
</script>

<template>
  <div>
    <span
      class="rounded-md border border-solid border-slate-700 bg-slate-800 px-2 py-1 text-xs text-slate-400"
      >{{ props.tag_name }}</span
    >
  </div>
</template>
