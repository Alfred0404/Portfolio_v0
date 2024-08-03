<script setup>
import NavItem from './NavItem.vue'
</script>

<template>
    <div class="w-3/5 m-4 items-center h-full font-bold">
        <ul class="flex justify-end items-center gap-3">
            <NavItem :name="'A propos de moi'" />
            <NavItem :name="'Projets'" />
            <NavItem :name="'Parcours'" />
            <NavItem :name="'Experiences'" />
            <NavItem :name="'Compétences'" />
        </ul>
    </div>
</template>