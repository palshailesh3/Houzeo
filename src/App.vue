<template>
  <div class="min-h-screen bg-gray-50">
    <!-- FIXED HEADER + FILTER -->
    <div class="sticky top-0 z-50 bg-white">
      <Header />
      <FilterBar />
    </div>

    <!-- CONTENT -->
    <div class="flex min-h-[calc(100vh-128px)]">
      <!-- MAP -->
      <MapSection
        v-if="isDesktop || activeView === 'map'"
      />

      <!-- LIST -->
      <div
        v-if="isDesktop || activeView === 'list'"
        class="w-full lg:w-[55%] bg-white border-l"
      >
        <SortBar />
        <PropertyList />
      </div>
    </div>

    <!-- MOBILE TOGGLE -->
    <MobileToggle
      :active="activeView"
      @change="activeView = $event"
    />
  </div>
</template>

<script setup>
import { ref, onMounted, onUnmounted } from "vue";

import Header from "./components/Header.vue";
import FilterBar from "./components/FilterBar.vue";
import MapSection from "./components/MapSection.vue";
import SortBar from "./components/SortBar.vue";
import PropertyList from "./components/PropertyList.vue";
import MobileToggle from "./components/MobileToggle.vue";

const activeView = ref("list");
const isDesktop = ref(window.innerWidth >= 1024);

const handleResize = () => {
  isDesktop.value = window.innerWidth >= 1024;
};

onMounted(() => {
  window.addEventListener("resize", handleResize);
});

onUnmounted(() => {
  window.removeEventListener("resize", handleResize);
});
</script>
