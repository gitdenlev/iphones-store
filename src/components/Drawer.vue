<script setup>
import CartItemList from './CartItemList.vue';
import { ref } from 'vue';
const showModal = ref(true);
</script>

<template>
  <div class="fixed top-o left-0 h-full w-full bg-black z-10 opacity-70"></div>
  <div v-show="showModal" class="bg-white w-96 h-full fixed right-0 top-0 z-20 p-8 overflow-y-scroll">
    <div class="flex items-center justify-between">
      <p class="text-2xl font-bold">Кошик</p>
      <img @click="showModal = !showModal" class="opacity-50 hover:opacity-100 transition-opacity" src="/svg/line.svg" alt="arrow" width="30" />
    </div>
    <CartItemList />

      <div class="flex mt-5">
        <span>Всього:</span>
        <div class="flex-1 border-b border-dashed"></div>
        <b>85 797 грн</b>
      </div>
    <button class="bg-lime-500 w-full rounded-xl py-3 mt-5 text-white cursor-pointer disabled:bg-slate-400 hover:bg-lime-600 active:bg-lime-700">Оформити замовлення</button>
  </div>
</template>
