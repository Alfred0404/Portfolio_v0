<script setup>
import NavItem from "./NavItem.vue";
</script>

<template>
  <div class="m-4 h-full w-3/5 items-center font-bold">
    <ul class="flex items-center justify-end gap-3">
      <NavItem :name="'A propos de moi'" />
      <NavItem :name="'Projets'" />
      <NavItem :name="'Parcours'" />
      <NavItem :name="'Experiences'" />
      <NavItem :name="'Compétences'" />
    </ul>
  </div>
</template>
