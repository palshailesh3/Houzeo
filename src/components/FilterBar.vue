<template>
  <div class="bg-white border-b">
    <div
      class="max-w-[1440px] mx-auto px-4 py-3
             flex items-center gap-3 overflow-x-auto"
    >
      <!-- SEARCH -->
      <div
        class="flex items-center gap-2
               border-2 border-blue-600
               rounded-full px-4 py-2
               min-w-[300px]"
      >
        <input
          type="text"
          value="Austin, TX"
          class="flex-1 text-sm outline-none bg-transparent"
        />

        <!-- CLEAR -->
        <svg
          class="w-4 h-4 text-gray-400 cursor-pointer"
          fill="none"
          stroke="currentColor"
          stroke-width="2"
          viewBox="0 0 24 24"
        >
          <path
            stroke-linecap="round"
            stroke-linejoin="round"
            d="M6 18L18 6M6 6l12 12"
          />
        </svg>

        <!-- SEARCH ICON -->
        <div
          class="bg-blue-600 rounded-full p-2
                 flex items-center justify-center cursor-pointer"
        >
          <svg
            class="w-4 h-4 text-white"
            fill="none"
            stroke="currentColor"
            stroke-width="2"
            viewBox="0 0 24 24"
          >
            <path
              stroke-linecap="round"
              stroke-linejoin="round"
              d="M21 21l-4.35-4.35M10 18a8 8 0 100-16 8 8 0 000 16z"
            />
          </svg>
        </div>
      </div>

      <!-- FOR SALE (ACTIVE) -->
      <button
        class="flex items-center gap-2
               border-2 border-blue-600
               text-blue-600 bg-blue-50
               rounded-full px-4 py-2
               text-sm font-medium whitespace-nowrap"
      >
        For Sale
        <Chevron />
      </button>

      <!-- OTHER FILTERS -->
      <FilterButton label="Price" />
      <FilterButton label="Beds & Baths" />
      <FilterButton label="Property Type" />

      <!-- FILTERS -->
      <button
        class="flex items-center gap-2
               border rounded-full px-4 py-2
               text-sm whitespace-nowrap
               hover:border-blue-600 transition"
      >
        <Sliders />
        Filters
      </button>

      <!-- SAVED -->
      <button
        class="flex items-center gap-2
               border rounded-full px-4 py-2
               text-sm whitespace-nowrap
               hover:border-blue-600 transition
               ml-auto"
      >
        <Bookmark />
        Saved
      </button>
    </div>
  </div>
</template>

<script setup>
import FilterButton from "./FilterButton.vue";

// ✅ CORRECT PATHS
import Chevron from "../icons/Chevron.vue";
import Sliders from "../icons/Sliders.vue";
import Bookmark from "../icons/Bookmark.vue";
</script>
