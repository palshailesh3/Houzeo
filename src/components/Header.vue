<template>
  <header class="bg-white border-b sticky top-0 z-50">
    <!-- TOP BAR -->
    <div
      class="max-w-[1440px] mx-auto h-[64px] px-4 md:px-6
             flex items-center justify-between"
    >
      <!-- LOGO -->
      <div class="flex items-center gap-1">
        <img src="/houzeo-logo.png" alt="Houzeo" class="h-7" />
        <span class="text-xs align-top">®</span>
      </div>

      <!-- DESKTOP NAV -->
      <nav class="hidden lg:flex items-center gap-6 text-sm text-gray-800">
        <NavItem label="Product" dropdown />
        <NavItem label="How Houzeo Works" />
        <NavItem label="Reviews" />
        <NavItem label="Buy" dropdown />
        <NavItem label="Sell" dropdown />
        <NavItem label="Pricing" />
        <NavItem label="Resources" dropdown />
        <NavItem label="Sign In" />
      </nav>

      <!-- RIGHT -->
      <div class="flex items-center gap-4">
        <button
          class="hidden md:block bg-[#1E5AA6] hover:bg-[#174A8A]
                 text-white text-sm font-semibold
                 px-5 py-2 rounded-md transition"
        >
          Start Free Listing
        </button>

        <!-- HAMBURGER -->
        <button class="lg:hidden p-2" @click="drawer = true">
          <svg
            class="w-6 h-6"
            fill="none"
            stroke="currentColor"
            stroke-width="2"
            viewBox="0 0 24 24"
          >
            <path stroke-linecap="round" stroke-linejoin="round"
              d="M4 6h16M4 12h16M4 18h16" />
          </svg>
        </button>
      </div>
    </div>

    <!-- BACKDROP -->
    <div
      v-if="drawer"
      class="fixed inset-0 bg-black/40 z-40"
      @click="drawer = false"
    />

    <!-- MOBILE DRAWER -->
    <aside
      class="fixed top-0 right-0 h-full w-[280px] bg-white z-50
             transform transition-transform duration-300
             lg:hidden flex flex-col"
      :class="drawer ? 'translate-x-0' : 'translate-x-full'"
    >
      <!-- HEADER -->
      <div class="h-[64px] px-4 flex items-center justify-between border-b">
        <span class="text-lg font-semibold">Menu</span>
        <button @click="drawer = false">✕</button>
      </div>

      <!-- MENU ITEMS -->
      <div class="flex-1 overflow-y-auto divide-y text-sm">
        <div
          v-for="item in menuItems"
          :key="item"
          class="px-4 py-4 cursor-pointer hover:bg-gray-50"
        >
          {{ item }}
        </div>
      </div>

      <!-- CTA -->
      <div class="p-4 border-t">
        <button
          class="w-full bg-[#1E5AA6] text-white py-2
                 rounded-md font-semibold"
        >
          Start Free Listing
        </button>
      </div>
    </aside>
  </header>
</template>

<script setup>
import { ref } from "vue";
import NavItem from "./NavItem.vue";

const drawer = ref(false);

const menuItems = [
  "Product",
  "How Houzeo Works",
  "Reviews",
  "Buy",
  "Sell",
  "Pricing",
  "Resources",
  "Sign In",
];
</script>
