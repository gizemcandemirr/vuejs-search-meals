<template>
  <div class="p-6">
    <input type="text" v-model="keyword" class="rounded border-2 border-gray-200 w-full" placeholder="Search for Meals"
      @change="searchMeals" />
  </div>

  <div v-for="meal of meals" :key="meal.idMeal">
    <div class="text-center">{{ meal.strMeal }}</div>
    <router-link :to="{ name: 'meal', params: { id: meal.idMeal } }">
      <div class="flex flex-col items-center">
        <img :src="meal.strMealThumb" class="w-32 h-32" />
        <div class="text-center">{{ meal.strMeal }}</div>
      </div>
    </router-link>
  </div>

</template>

<script setup>
import { computed, ref } from "vue";
import store from "../store";

const keyword = ref("");
const meals = computed(() => store.state.searchedMeals);

function searchMeals() {
  store.dispatch("searchMeals", keyword.value);
}
</script>
