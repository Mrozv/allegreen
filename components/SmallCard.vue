<template>
  <li class="flex flex-col align-middle shadow-xl w-full max-sm:min-w-3/8">
    <div
      class="h-32 bg-cover bg-center"
      :style="`background-image: url(images/${imageUrl})`"
    ></div>
    <div class="p-2 flex flex-col items-center">
      <span class="text-green-600 font-semibold">{{ price }} zł</span>
      <p class="text-gray-400 text-sm">{{ title }}</p>
    </div>
  </li>
</template>

<script setup>
const props = defineProps({
  title: {
    type: String,
    default: "Nazwa produktu",
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
