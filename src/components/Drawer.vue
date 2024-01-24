<script setup>
import CartItem from './CartItem.vue';
</script>

<template>
  <div class="fixed top-o left-0 h-full w-full bg-black z-10 opacity-70"></div>
  <div class="bg-white w-96 h-full fixed right-0 top-0 z-20 p-8 overflow-y-scroll">
    <div class="flex items-center justify-between">
      <p class="text-2xl font-bold">Кошик</p>
      <img class="opacity-50 hover:opacity-100 transition-opacity" src="/svg/line.svg" alt="arrow" width="30" />
    </div>
    <CartItem />
    <CartItem />
    <CartItem />
    <CartItem />
    <CartItem />
    <CartItem />
  </div>
</template>
