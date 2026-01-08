<template>
  <div class="p-6 grid grid-cols-1 md:grid-cols-2 gap-6">
    <PropertyCard
      v-for="item in properties"
      :key="item.id"
      v-bind="item"
    />
  </div>
</template>

<script setup>
import PropertyCard from "./PropertyCard.vue";
import properties from "../data/properties";
</script>
