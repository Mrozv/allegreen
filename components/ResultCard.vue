<template>
  <li
    class="flex align-middle shadow-xl w-full bg-white rounded overflow-hidden"
  >
    <div
      class="h-full w-48 max-sm:w-3/4 max-sm:h-auto bg-cover bg-center"
      :style="`background-image: url(images/${imageUrl})`"
    ></div>
    <div class="p-4 flex flex-col gap-2 w-full">
      <NuxtLink
        class="font-bold text-xl text-gray-600"
        :to="{
          path: `/products/${id}`,
          query: { title, description, price, imageUrl },
        }"
      >
        {{ title }}
      </NuxtLink>
      <p class="text-gray-400 text-sm">{{ description }}</p>
      <span class="text-green-600 font-semibold">{{ price }} zł</span>
      <NuxtLink
        class="py-2 px-8 font-medium cursor-pointer bg-green-600 text-white w-fit"
        :to="{
          path: `/cart`,
          query: { title, description, price, imageUrl },
        }"
      >
        Dodaj do koszyka
      </NuxtLink>
    </div>
  </li>
</template>

<script setup>
import { NuxtLink } from "#components";

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
