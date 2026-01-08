<template>
  <button
    class="flex items-center gap-2
           border rounded-full px-4 py-2
           text-sm whitespace-nowrap
           hover:border-blue-600 transition"
  >
    {{ label }}
    <Chevron />
  </button>
</template>

<script setup>
import Chevron from "../icons/Chevron.vue"; // ✅ CORRECT
defineProps({
  label: String,
});
</script>
