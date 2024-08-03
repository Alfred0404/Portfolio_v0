<script setup>
import { defineProps } from 'vue';

const props = defineProps(['name']);

const HandlescrollToElement = () => {
    // const element = document.querySelector(`#${props.name}`);
    console.log("scrolling to ", props.name);
    element.scrollIntoView({ behavior: 'smooth' });
}


</script>

<template>
    <button @click="HandlescrollToElement" class="text-slate-950 p-2 px-6 rounded-lg bg-slate-50 hover:bg-emerald-400 hover:cursor-pointer transition">
        {{ $props.name }}
    </button>
</template>