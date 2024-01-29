<!-- <script setup>
import Card from "./Card.vue";
defineProps({
  items: Array,
});


onMounted(async () => {
  try {
    const { data } = await axios.get(
      `https://${API_KEY}.mockapi.io/items`
    );
    items.value = data;
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
</template> -->
