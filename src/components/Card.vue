  <script setup>
  import Like from "./Like.vue";
  defineProps({
    title: String,
    price: String,
    imgUrl: String,
  })
  </script>

  <template>
    <div
      class="relative bg-white border border-slate-100 p-8 rounded-3xl cursor-pointer transition hover:-translate-y-1 hover:shadow-xl"
    >
      <Like class="absolute top-9 left-10" />
      <img class="rounded-lg" :src="imgUrl" alt="iphone" width="150" />
      <p class="mt-2">{{ title }}</p>
      <div class="flex justify-between mt-1">
        <div class="flex flex-col">
          <span class="text-slate-600">Ціна:</span>
          <b>{{ price }} грн</b>
        </div>
        <button class="disabled:bg-slate-400 bg-green-500 hover:bg-green-700 text-white font-bold py-2 px-4 rounded">
        Купити
      </button>
      </div>
    </div>
  </template>
