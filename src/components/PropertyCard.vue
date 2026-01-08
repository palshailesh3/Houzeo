<template>
  <div
    class="border rounded-lg overflow-hidden bg-white
           transition-shadow duration-300
           hover:shadow-[0_8px_24px_rgba(0,0,0,0.12)]"
  >
    <!-- IMAGE -->
    <div class="relative group">
      <img
        :src="images[current]"
        class="h-52 w-full object-cover"
        loading="lazy"
      />

      <!-- BADGE -->
      <span
        class="absolute top-2 left-2 bg-white text-xs px-2 py-1 rounded"
      >
        {{ days }}
      </span>

      <!-- HEART -->
      <button
        class="absolute top-2 right-2 bg-white rounded-full p-2
               hover:animate-pulse"
      >
        ♥
      </button>

      <!-- SLIDER CONTROLS -->
      <button
        v-if="current > 0"
        @click="prev"
        class="hidden group-hover:block
               absolute top-1/2 left-2 -translate-y-1/2
               bg-white px-3 py-1 rounded shadow"
      >
        ‹
      </button>

      <button
        v-if="current < images.length - 1"
        @click="next"
        class="hidden group-hover:block
               absolute top-1/2 right-2 -translate-y-1/2
               bg-white px-3 py-1 rounded shadow"
      >
        ›
      </button>

      <!-- DOTS -->
      <div
        class="absolute bottom-2 left-1/2 -translate-x-1/2
               flex gap-1"
      >
        <span
          v-for="(_, i) in images"
          :key="i"
          class="w-1.5 h-1.5 rounded-full bg-white opacity-50"
          :class="{ 'opacity-100': i === current }"
        />
      </div>
    </div>

    <!-- CONTENT -->
    <div class="p-4 space-y-1">
      <p class="text-xs text-green-700 font-medium flex items-center gap-1">
        ● {{ type }}
      </p>

      <h3 class="text-blue-600 font-bold text-lg">
        {{ price }}
      </h3>

      <p class="text-sm text-gray-700">
        <span class="font-semibold text-blue-600">{{ beds }}</span> Beds ·
        <span class="font-semibold text-blue-600">{{ baths }}</span> Baths ·
        <span class="font-semibold text-blue-600">{{ sqft }}</span> sqft
      </p>

      <p class="text-sm text-gray-800">
        {{ address }}
      </p>

      <p class="text-xs text-gray-500 mt-1">
        MLS-TN as distributed by MLS GRID
      </p>
    </div>
  </div>
</template>

<script setup>
import { ref } from "vue";

defineProps({
  images: Array,
  type: String,
  price: String,
  beds: Number,
  baths: Number,
  sqft: Number,
  address: String,
  days: String,
});

const current = ref(0);
const next = () => current.value++;
const prev = () => current.value--;
</script>
