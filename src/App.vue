<script setup>
import Header from "./components/Header.vue";
import Drawer from "./components/Drawer.vue";
import Card from "./components/Card.vue";
import { onMounted, reactive, ref, watch } from "vue";
import axios from "axios";

// Return items from API
const items = ref([]);
const API_KEY = "65b773df46324d531d549d38";



const filtres = reactive({
  sortBy: "",
  searchQuery: ""
})


const onChangeSelect = event => {
  filtres.sortBy = event.target.value;
};



onMounted(async () => {
  try {
    const { data } = await axios.get(`https://${API_KEY}.mockapi.io/items`);
    items.value = data;
  } catch (error) {
    console.log(error);
  }
});

watch(filtres, async () => {
  try {
    const { data } = await axios.get(`https://${API_KEY}.mockapi.io/items?sortBy=` + filtres.sortBy);
    items.value = data;
  } catch (error) {
    console.log(error);
  }
});
</script>

<template>
  <!-- <Drawer /> -->
  <div class="bg-white m-auto rounded-xl shadow-xl">
    <Header />
    <div class="p-10">
      <div class="flex justify-between items-center">
        <h2 class="text-3xl font-bold mb-8">Всі моделі</h2>
        <div class="flex gap-4">
          <select
            @change="onChangeSelect"
            class="bg-gray-100 text-slate-600 px-2.5 text-center w-100 h-10 rounded-md outline-none shadow-md"
          >
            <option value="price">Спочатку дешеві</option>
            <option value="-price">Спочатку дорогі</option>
          </select>
          <div class="relative">
            <img
              class="absolute left-3 top-2"
              src="/svg/search.svg"
              alt="search"
              width="24"
            />
            <input
              class="bg-gray-100 py-2 pl-10 pr-4 rounded-md text-black outline-none shadow-md"
              type="text"
              placeholder="Пошук"
            />
          </div>
        </div>
      </div>

      <div class="grid grid-cols-4 gap-5 mt-4">
        <Card
          v-for="item in items"
          :key="item.id"
          :title="item.title"
          :price="item.price"
          :imgUrl="item.imgUrl"
        />
      </div>
    </div>
  </div>
</template>

<style scoped></style>
