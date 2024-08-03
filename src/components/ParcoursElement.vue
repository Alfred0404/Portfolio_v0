<script setup>
import { onMounted, ref } from "vue";

const props = defineProps(["periode", "statut", "diplome", "etablissement"]);
const elementRef = ref(null);

onMounted(() => {
  const parent = elementRef.value.parentElement;
  const children = parent.children;
  if (children[children.length - 1] === elementRef.value) {
    elementRef.value
      .querySelector("div")
      .style.setProperty("--after-display", "none");
  }
});
</script>

<template>
  <div ref="elementRef" class="bg-slate-950 text-slate-50">
    <div
      class="group relative flex cursor-pointer flex-col items-start py-10 ps-10 text-slate-400 after:absolute after:left-[8px] after:top-20 after:z-10 after:h-3/4 after:w-0.5 after:bg-slate-900"
      :style="{ '--after-display': 'block' }"
    >
      <p
        class="relative text-xl font-bold text-slate-50 transition group-hover:text-emerald-400"
      >
        {{ props.periode }}
      </p>
      <div class="mt-4 flex flex-row items-center justify-start gap-4">
        <svg
          width="24"
          height="24"
          viewBox="0 0 24 24"
          fill="none"
          xmlns="http://www.w3.org/2000/svg"
        >
          <g id="SVGRepo_bgCarrier" stroke-width="0"></g>
          <g
            id="SVGRepo_tracerCarrier"
            stroke-linecap="round"
            stroke-linejoin="round"
          ></g>
          <g id="SVGRepo_iconCarrier">
            <path
              d="M22 9L12 4L2 9L12 14L22 9ZM22 9V15M19 10.5V16.5L12 20L5 16.5V10.5"
              stroke="#475569"
              stroke-width="2"
              stroke-linecap="round"
              stroke-linejoin="round"
            ></path>
          </g>
        </svg>
        <p class="transition group-hover:text-emerald-500">
          {{ props.diplome }}
        </p>
      </div>
      <div class="mb-4 mt-1 flex flex-row items-center justify-start gap-4">
        <svg
          width="24px"
          height="24px"
          viewBox="0 0 24 24"
          fill="none"
          xmlns="http://www.w3.org/2000/svg"
        >
          <g id="SVGRepo_bgCarrier" stroke-width="0"></g>
          <g
            id="SVGRepo_tracerCarrier"
            stroke-linecap="round"
            stroke-linejoin="round"
          ></g>
          <g id="SVGRepo_iconCarrier">
            <path
              d="M12 21C15.5 17.4 19 14.1764 19 10.2C19 6.22355 15.866 3 12 3C8.13401 3 5 6.22355 5 10.2C5 14.1764 8.5 17.4 12 21Z"
              stroke="#475569"
              stroke-width="2"
              stroke-linecap="round"
              stroke-linejoin="round"
            ></path>
            <path
              d="M12 13C13.6569 13 15 11.6569 15 10C15 8.34315 13.6569 7 12 7C10.3431 7 9 8.34315 9 10C9 11.6569 10.3431 13 12 13Z"
              stroke="#475569"
              stroke-width="2"
              stroke-linecap="round"
              stroke-linejoin="round"
            ></path>
          </g>
        </svg>
        <p class="transition group-hover:text-emerald-500">
          {{ props.etablissement }}
        </p>
      </div>
      <div
        class="absolute -left-1 h-6 w-6 rounded-full bg-slate-600"
        v-if="props.statut === 'check'"
      ></div>
      <svg
      class="absolute -left-1 h-7 w-7"
        v-if="props.statut === 'en_cours'"
        width="32px"
        height="32px"
        viewBox="0 0 24 24"
        fill="none"
        xmlns="http://www.w3.org/2000/svg"
      >
        <g id="SVGRepo_bgCarrier" stroke-width="0"></g>
        <g
          id="SVGRepo_tracerCarrier"
          stroke-linecap="round"
          stroke-linejoin="round"
        ></g>
        <g id="SVGRepo_iconCarrier">
          <path
            d="M19.9381 13C19.979 12.6724 20 12.3387 20 12C20 7.58172 16.4183 4 12 4C9.49942 4 7.26681 5.14727 5.7998 6.94416M4.06189 11C4.02104 11.3276 4 11.6613 4 12C4 16.4183 7.58172 20 12 20C14.3894 20 16.5341 18.9525 18 17.2916M15 17H18V17.2916M5.7998 4V6.94416M5.7998 6.94416V6.99993L8.7998 7M18 20V17.2916"
            stroke="#475569"
            stroke-width="2"
            stroke-linecap="round"
            stroke-linejoin="round"
          ></path>
        </g>
      </svg>
    </div>
  </div>
</template>

<style scoped>
div::after {
  display: var(--after-display);
}
</style>
