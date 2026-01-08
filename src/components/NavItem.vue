<template>
  <div
    class="flex items-center gap-1 cursor-pointer
           hover:text-blue-700 transition"
  >
    <span>{{ label }}</span>

    <svg
      v-if="dropdown"
      class="w-3 h-3 mt-[1px]"
      fill="currentColor"
      viewBox="0 0 20 20"
    >
      <path
        fill-rule="evenodd"
        d="M5.23 7.21a.75.75 0 011.06.02L10 11.06l3.71-3.83a.75.75 0 111.08 1.04l-4.25 4.38a.75.75 0 01-1.08 0L5.21 8.27a.75.75 0 01.02-1.06z"
        clip-rule="evenodd"
      />
    </svg>
  </div>
</template>

<script setup>
defineProps({
  label: String,
  dropdown: Boolean,
});
</script>
