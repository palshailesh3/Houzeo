<template>
  <div
    class="fixed bottom-4 left-1/2 -translate-x-1/2 z-50
           lg:hidden bg-white shadow-lg rounded-full flex overflow-hidden"
  >
    <button
      class="px-6 py-2 text-sm font-semibold transition"
      :class="active === 'map'
        ? 'bg-blue-600 text-white'
        : 'text-blue-600'"
      @click="setView('map')"
    >
      Map
    </button>

    <button
      class="px-6 py-2 text-sm font-semibold transition"
      :class="active === 'list'
        ? 'bg-blue-600 text-white'
        : 'text-blue-600'"
      @click="setView('list')"
    >
      List
    </button>
  </div>
</template>

<script setup>
const props = defineProps({
  active: {
    type: String,
    default: "list",
  },
});

const emit = defineEmits(["change"]);

const setView = (view) => {
  emit("change", view);
};
</script>
