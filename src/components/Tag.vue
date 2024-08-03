<script setup>
import { defineProps } from 'vue';

const props = defineProps(['tag_name']);
</script>

<template>
    <div>
        <span class="bg-slate-800 border border-solid border-slate-700 text-slate-400 px-2 py-1 mx-10 rounded-md">{{ props.tag_name }}</span>
    </div>
</template>