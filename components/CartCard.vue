<template>
  <li
    class="flex align-middle shadow-xl w-full bg-white rounded overflow-hidden"
  >
    <div
      class="h-full w-48 max-sm:w-3/4 max-sm:h-auto bg-cover bg-center"
      :style="`background-image: url(/images/${imageUrl})`"
    ></div>
    <div class="flex justify-between w-full pr-4">
      <div class="p-4 flex flex-col gap-2">
        <h1 class="font-bold text-xl">{{ title }}</h1>
        <p class="text-gray-400 text-sm">{{ description }}</p>
      </div>
      <div
        class="flex items-center gap-2 max-sm:flex-col max-sm:justify-center"
      >
        <button
          class="bg-green-600 rounded text-white font-semibold py-2 px-4 cursor-pointer"
        >
          -
        </button>
        <span>1</span>
        <button
          class="bg-green-600 rounded text-white font-semibold py-2 px-4 cursor-pointer"
        >
          +
        </button>
        <span
          class="text-green-600 text-nowrap flex items-center font-semibold"
        >
          {{ price }} zł
        </span>
      </div>
    </div>
  </li>
</template>

<script setup>
const props = defineProps({
  title: {
    type: String,
    default: "Nazwa produktu",
  },
  description: {
    type: String,
    default: "Opis produktu",
  },
  price: {
    type: [Number, String],
    default: "Cena produktu",
  },
  imageUrl: {
    type: String,
  },
  id: {
    type: [Number, String],
    required: true,
  },
});
</script>
