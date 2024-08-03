<script setup>
// import { defineProps } from 'vue'
import Tag from './Tag.vue'

const props = defineProps(['name', 'tag_name', 'description', 'stack', 'image_path', 'link'])
</script>

<template>
    <div class="w-96 h-fit overflow-hidden bg-slate-900 flex flex-col justify-start gap-5 rounded-xl border-solid border border-slate-700">
        <img class="border-solid border-b border-slate-700 object-cover h-48" :src="props.image_path" alt="project image">
        <Tag class="mb-5" :tag_name="props.tag_name"/>
        <h1 class="text-3xl px-10">{{ props.name }}</h1>
        <p class=" px-10 text-slate-400">{{ props.description }}</p>
        <ul class="flex flex-row justify-start items-center gap-2 px-10">
            <li v-for="item in props.stack" :key="item"><img class="w-12" :src="`src/assets/logo_${item}.png`" :alt="`${item} logo`"></li>
        </ul>
        <a class="font-bold text-slate-950 p-2 px-8 mx-10 my-10 rounded-lg bg-slate-50 w-fit hover:bg-emerald-400 hover:cursor-pointer transition" :href="props.link" target="_blank">En voir plus</a>
    </div>
</template>