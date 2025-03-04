<script setup>
import Tag from "./Tag.vue";
import { onMounted, ref } from "vue";

const props = defineProps([
  "periode",
  "status",
  "experience",
  "entreprise",
  "competences",
  "contrat",
]);
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
      class="group relative flex flex-col items-start py-10 ps-10 text-slate-400 after:absolute after:left-[8px] after:top-20 after:z-10 after:h-4/5 after:w-0.5 after:bg-slate-900"
      :style="{ '--after-display': 'block' }"
    >
      <p
        class="relative text-lg font-bold text-slate-50 transition group-hover:text-emerald-400"
      >
        {{ props.periode }}
      </p>
      <div class="mb-1 mt-2 flex flex-row items-center justify-start gap-4">
        <p
          class="text-md text-slate-300 transition group-hover:text-emerald-500"
        >
          {{ props.contrat }}
        </p>
      </div>
      <div class="mt-1 flex flex-row items-center justify-start gap-4">
        <svg
          class="min-h-[20px] min-w-[20px]"
          width="20px"
          height="20px"
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
              d="M3.02747 10.022L6.68521 12.9482C7.17251 13.338 7.41617 13.5329 7.68749 13.6715C7.9282 13.7945 8.18443 13.8844 8.44921 13.9387C8.74767 14 9.0597 14 9.68375 14H14.3163C14.9403 14 15.2523 14 15.5508 13.9387C15.8156 13.8844 16.0718 13.7945 16.3125 13.6715C16.5838 13.5329 16.8275 13.338 17.3148 12.9482L20.9725 10.022M3.02747 10.022C3 10.4895 3 11.0642 3 11.8V16.2C3 17.8802 3 18.7202 3.32698 19.362C3.6146 19.9265 4.07354 20.3854 4.63803 20.673C5.27976 21 6.11984 21 7.8 21H16.2C17.8802 21 18.7202 21 19.362 20.673C19.9265 20.3854 20.3854 19.9265 20.673 19.362C21 18.7202 21 17.8802 21 16.2V11.8C21 11.0642 21 10.4895 20.9725 10.022M3.02747 10.022C3.06272 9.42205 3.1432 8.99871 3.32698 8.63803C3.6146 8.07354 4.07354 7.6146 4.63803 7.32698C5.27976 7 6.11984 7 7.8 7H8M20.9725 10.022C20.9373 9.42205 20.8568 8.99871 20.673 8.63803C20.3854 8.07354 19.9265 7.6146 19.362 7.32698C18.7202 7 17.8802 7 16.2 7H16M8 7V6C8 4.34315 9.34315 3 11 3H13C14.6569 3 16 4.34315 16 6V7M8 7H16"
              stroke="#475569"
              stroke-width="2"
              stroke-linecap="round"
              stroke-linejoin="round"
            ></path>
          </g>
        </svg>
        <p class="text-sm transition group-hover:text-emerald-500">
          {{ props.experience }}
        </p>
      </div>
      <div class="mb-4 mt-1 flex flex-row items-center justify-start gap-4">
        <svg
          class="min-h-[20px] min-w-[20px]"
          width="20px"
          height="20px"
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
              d="M18 21V22C18.5523 22 19 21.5523 19 21H18ZM6 21H5C5 21.5523 5.44772 22 6 22V21ZM17.454 3.10899L17 4L17.454 3.10899ZM17.891 3.54601L17 4L17.891 3.54601ZM6.54601 3.10899L7 4L6.54601 3.10899ZM6.10899 3.54601L7 4L6.10899 3.54601ZM9 6C8.44772 6 8 6.44772 8 7C8 7.55228 8.44772 8 9 8V6ZM10 8C10.5523 8 11 7.55228 11 7C11 6.44772 10.5523 6 10 6V8ZM9 9C8.44772 9 8 9.44772 8 10C8 10.5523 8.44772 11 9 11V9ZM10 11C10.5523 11 11 10.5523 11 10C11 9.44772 10.5523 9 10 9V11ZM14 9C13.4477 9 13 9.44772 13 10C13 10.5523 13.4477 11 14 11V9ZM15 11C15.5523 11 16 10.5523 16 10C16 9.44772 15.5523 9 15 9V11ZM14 12C13.4477 12 13 12.4477 13 13C13 13.5523 13.4477 14 14 14V12ZM15 14C15.5523 14 16 13.5523 16 13C16 12.4477 15.5523 12 15 12V14ZM9 12C8.44772 12 8 12.4477 8 13C8 13.5523 8.44772 14 9 14V12ZM10 14C10.5523 14 11 13.5523 11 13C11 12.4477 10.5523 12 10 12V14ZM14 6C13.4477 6 13 6.44772 13 7C13 7.55228 13.4477 8 14 8V6ZM15 8C15.5523 8 16 7.55228 16 7C16 6.44772 15.5523 6 15 6V8ZM7.6 4H16.4V2H7.6V4ZM17 4.6V21H19V4.6H17ZM18 20H6V22H18V20ZM7 21V4.6H5V21H7ZM16.4 4C16.6965 4 16.8588 4.00078 16.9754 4.0103C17.0803 4.01887 17.0575 4.0293 17 4L17.908 2.21799C17.6366 2.07969 17.3668 2.03562 17.1382 2.01695C16.9213 1.99922 16.6635 2 16.4 2V4ZM19 4.6C19 4.33647 19.0008 4.07869 18.9831 3.86177C18.9644 3.63318 18.9203 3.36344 18.782 3.09202L17 4C16.9707 3.94249 16.9811 3.91972 16.9897 4.02463C16.9992 4.14122 17 4.30347 17 4.6H19ZM17 4L18.782 3.09202C18.5903 2.7157 18.2843 2.40973 17.908 2.21799L17 4ZM7.6 2C7.33647 2 7.07869 1.99922 6.86177 2.01695C6.63318 2.03562 6.36344 2.07969 6.09202 2.21799L7 4C6.94249 4.0293 6.91972 4.01887 7.02463 4.0103C7.14122 4.00078 7.30347 4 7.6 4V2ZM7 4.6C7 4.30347 7.00078 4.14122 7.0103 4.02463C7.01887 3.91972 7.0293 3.94249 7 4L5.21799 3.09202C5.07969 3.36344 5.03562 3.63318 5.01695 3.86177C4.99922 4.07869 5 4.33647 5 4.6H7ZM6.09202 2.21799C5.71569 2.40973 5.40973 2.71569 5.21799 3.09202L7 4L6.09202 2.21799ZM9 8H10V6H9V8ZM9 11H10V9H9V11ZM14 11H15V9H14V11ZM14 14H15V12H14V14ZM9 14H10V12H9V14ZM14 8H15V6H14V8ZM13 18V21H15V18H13ZM11 21V18H9V21H11ZM12 17C12.5523 17 13 17.4477 13 18H15C15 16.3431 13.6569 15 12 15V17ZM12 15C10.3431 15 9 16.3431 9 18H11C11 17.4477 11.4477 17 12 17V15Z"
              fill="#475569"
            ></path>
          </g>
        </svg>
        <p class="text-sm transition group-hover:text-emerald-500">
          {{ props.entreprise }}
        </p>
      </div>
      <ul class="flex max-w-lg flex-wrap">
        <li v-for="competence in props.competences" :key="competence">
          <Tag class="mr-2 mt-4" :tag_name="competence" />
        </li>
      </ul>
      <div
        class="absolute -left-0 h-5 w-5 rounded-full bg-slate-600"
        v-if="props.status === 'check'"
      ></div>
      <svg
        class="absolute -left-1 h-7 min-h-[20px] w-7 min-w-[20px]"
        v-if="props.status === 'en_cours'"
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
