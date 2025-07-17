<template>
  <li class="flex flex-col align-middle shadow-xl w-full">
    <div
      class="h-48 w-full bg-cover bg-center"
      :style="`background-image: url(images/${imageUrl})`"
    ></div>
    <div class="p-4 flex flex-col gap-2">
      <h1 class="font-bold text-xl">{{ title }}</h1>
      <p class="text-gray-400 text-sm">{{ description }}</p>
      <span class="text-green-600 font-semibold">{{ price }} zł</span>
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
    default: 0,
  },
  imageUrl: {
    type: String,
  },
});
</script>

<style scoped></style>
