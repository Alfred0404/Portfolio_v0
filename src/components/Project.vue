<script setup>
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
    class="flex h-fit w-80 flex-col justify-start gap-3 overflow-hidden rounded-xl border border-solid border-slate-700 bg-slate-900"
  >
    <img
      class="h-48 border-b border-solid border-slate-700 object-cover"
      :src="props.image_path"
      alt="project image"
    />
    <Tag class="mx-6 mb-3" :tag_name="props.tag_name" />
    <h1 class="mx-6 text-2xl">{{ props.name }}</h1>
    <p class="mx-6 text-xs text-slate-400">{{ props.description }}</p>
    <ul class="mx-6 flex flex-row items-center justify-start gap-2">
      <li v-for="item in props.stack" :key="item">
        <img
          class="w-12"
          :src="`/logo_${item}.png`"
          :alt="`${item} logo`"
        />
      </li>
    </ul>
    <a
      class="mx-6 my-6 w-fit rounded-lg bg-slate-50 p-2 px-8 text-xs font-bold text-slate-950 transition hover:cursor-pointer hover:bg-emerald-400"
      :href="props.link"
      target="_blank"
      >En voir plus</a
    >
  </div>
</template>
