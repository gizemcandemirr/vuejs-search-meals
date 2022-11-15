<script setup></script>

<template>
  <div class="bg-gray-100">
    <header class="bg-white shadow-md h-16 flex justify-between items-stretch px-6">
      <router-link
        :to="{ name: 'home' }"
        class="inline-flex items-center h-full"
      >
        Home
      </router-link>
      <div class="flex items-center gap-1">
        <router-link
          to="/"
          class="inline-flex items-center transition-colors px-2 h-full hover:bg-purple-100"
        >
          Search Meals
        </router-link>
        <router-link
          to="/"
          class="inline-flex items-center transition-colors px-2 h-full hover:bg-purple-100"
        >
          Meals By Letter</router-link
        >
        <router-link
          to="/"
          class="inline-flex items-center transition-colors px-2 h-full hover:bg-purple-100"
        >
          Meals By Ingredients
        </router-link>
      </div>
    </header>
  </div>
  <main>
    <router-view />
  </main>
</template>

<style scoped></style>
