<script setup>
import Header from "./components/Header.vue";
import Drawer from "./components/Drawer.vue";
import Card from "./components/Card.vue";
import CardList from "./components/CardList.vue";
import Filter from "./components/Filter.vue";
</script>

<template>
  <!-- <Drawer /> -->
  <div class="bg-white w-4/5 m-auto rounded-xl shadow-xl">
    <Header />
    <div class="p-10">
      <div class="flex justify-between items-center">
        <h2 class="text-3xl font-bold mb-8">Всі моделі</h2>
        <Filter />
      </div>
      <CardList />
    </div>
  </div>
</template>

<style scoped></style>
