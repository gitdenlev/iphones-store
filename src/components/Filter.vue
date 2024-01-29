<template>
  <div class="flex gap-4">
    <select
      class="bg-gray-100 text-slate-600 px-2.5 text-center w-100 h-10 rounded-md outline-none shadow-md"
    >
      <option value="1">Спочатку дешеві</option>
      <option value="2">Спочатку дорогі</option>
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
</template>
