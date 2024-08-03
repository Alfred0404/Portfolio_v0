<script setup>
// import { defineProps } from 'vue'
import Tag from "./Tag.vue";

const props = defineProps([
  "name",
  "tag_name",
  "description",
  "stack",
  "image_path",
  "link",
]);
</script>

<template>
  <div
    class="flex h-fit w-96 flex-col justify-start gap-5 overflow-hidden rounded-xl border border-solid border-slate-700 bg-slate-900"
  >
    <img
      class="h-48 border-b border-solid border-slate-700 object-cover"
      :src="props.image_path"
      alt="project image"
    />
    <Tag class="mx-10 mb-5" :tag_name="props.tag_name" />
    <h1 class="px-10 text-3xl">{{ props.name }}</h1>
    <p class="px-10 text-slate-400">{{ props.description }}</p>
    <ul class="flex flex-row items-center justify-start gap-2 px-10">
      <li v-for="item in props.stack" :key="item">
        <img
          class="w-12"
          :src="`src/assets/logo_${item}.png`"
          :alt="`${item} logo`"
        />
      </li>
    </ul>
    <a
      class="mx-10 my-10 w-fit rounded-lg bg-slate-50 p-2 px-8 font-bold text-slate-950 transition hover:cursor-pointer hover:bg-emerald-400"
      :href="props.link"
      target="_blank"
      >En voir plus</a
    >
  </div>
</template>
