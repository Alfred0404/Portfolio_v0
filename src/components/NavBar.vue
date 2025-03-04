<script setup>
import NavItem from "./NavItem.vue";
</script>

<template>
  <div
    class="m-4 h-full w-5/6 flex-row items-center justify-end font-bold hidden lg:flex"
  >
    <ul class="flex items-center justify-end gap-3">
      <!-- <NavItem :name="'A propos de moi'" /> -->
      <NavItem :name="'Compétences'" />
      <NavItem :name="'Projets'" />
      <NavItem :name="'Parcours'" />
      <NavItem :name="'Experiences'" />
    </ul>
    <a
      class="ms-6 rounded-lg bg-slate-50 p-2 px-6 text-sm text-slate-950 transition hover:cursor-pointer hover:bg-emerald-400"
      href="mailto:alfreddevulpian04@gmail.com"
      >Me contacter</a
    >
  </div>
</template>
