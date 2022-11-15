<template>
  <div class="p-8 flex flex-col">
    <div>
      <input
        class="rounded border-2 border-gray-200 w-full"
        type="text"
        placeholder="Search for Meals"
      />
    </div>

    <div class="flex justify-center gap-2 mt-2">
      <router-link
        :to="{ name: 'byLetter', params: { letter } }"
        v-for="letter of letters"
        :key="letter"
      >
        {{ letter }}</router-link
      >
    </div>
  </div>
</template>

<script setup>
import { computed } from "vue";
import store from "../store";

const meals = computed(() => store.state.meals);
const letters = "ABJFGJEFLJGFFGŞFLG".split("");
</script>
