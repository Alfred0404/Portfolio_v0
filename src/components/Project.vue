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
    class="overflow-hidden rounded-xl border border-solid border-slate-700 bg-slate-900"
  >
    <a
      class="flex h-fit w-80 flex-col justify-start gap-3"
      :href="props.link"
      target="_blank"
    >
      <img
        class="h-48 border-solid border-slate-700 object-cover"
        :src="props.image_path"
        alt="project image"
      />
      <h1 class="mx-6 text-2xl">{{ props.name }}</h1>
      <Tag class="mx-6 my-3" :tag_name="props.tag_name" />
      <ul class="mx-6 flex flex-row items-center justify-start gap-2 pb-6">
        <li
          v-for="item in props.stack"
          :key="item"
          class="flex h-8 w-8 items-center justify-center"
        >
          <img
            class="object-cover"
            :src="`/logo_${item.toLowerCase()}.png`"
            :alt="`${item.toLowerCase()} logo!!!`"
          />
        </li>
      </ul>
    </a>
  </div>
</template>
