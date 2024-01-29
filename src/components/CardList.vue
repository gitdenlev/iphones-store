<script setup>
import Card from "./Card.vue";
defineProps({
  items: Array,
});

import { onMounted, ref } from "vue";
import axios from "axios";

const items = ref([]);

onMounted(async () => {
  try {
    const { data } = await axios.get("https://65b773df46324d531d549d38.mockapi.io/items");
    items.value = data;
    console.log(data);
  } catch (error) {
    console.log(error);
  }
});
</script>

<template>
  <div class="grid grid-cols-4 gap-5 mt-4">
    <Card
      v-for="item in items"
      :key="item.id"
      :title="item.title"
      :price="item.price"
      :imgUrl="item.imgUrl"
    />
  </div>
</template>
