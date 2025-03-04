<script setup>
import Contact from "./Contact.vue";
</script>

<template>
  <div
    class="flex flex-col items-center justify-center bg-slate-950 py-10 text-xs text-slate-50"
  >
    <Contact class="mb-10" />
    <a
      class="mx-10 mb-10 w-fit rounded-lg border border-solid border-slate-600 p-4 px-10 text-sm font-bold text-slate-50 transition hover:cursor-pointer hover:border-slate-400 hover:bg-slate-900"
      href="https://github.com/Alfred0404/Portfolio_v0"
      target="_blank"
      >Repo du projet</a
    >
    <ul
      class="flex flex-col items-center justify-evenly gap-4 md:flex-row md:gap-10"
    >
      <li><p>© Alfred de Vulpian - 2024 - tous droits réservés</p></li>
      <li>
        <a
          class="transition hover:text-emerald-400"
          href="https://www.svgrepo.com/collection/dazzle-line-icons/"
          target="_blank"
          >svgs collection</a
        >
      </li>
      <li>
        <a
          class="transition hover:text-emerald-400"
          href="https://icones8.fr/icons"
          target="_blank"
          >icons</a
        >
      </li>
      <li>
        <a
          class="transition hover:text-emerald-400"
          href="https://tailwindcss.com"
          target="_blank"
          >tailwind documentation</a
        >
      </li>
    </ul>
  </div>
</template>
