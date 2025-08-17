<template>
  <div
    class="flex flex-col align-middle shadow-xl bg-white rounded p-4 gap-4 w-1/4 max-sm:w-full"
  >
    <div class="flex flex-col gap-2">
      <h1 class="font-bold text-xl">{{ title }}</h1>
      <span class="text-green-600 font-semibold text-2xl">{{ price }} zł</span>
      <p class="text-gray-400 text-sm">{{ description }}</p>
    </div>
    <div class="flex justify-between gap-4">
      <div class="flex flex-col w-full">
        <label class="font-bold text-gray-600 text-sm" for="">Długość</label>
        <div
          class="flex justify-between items-center w-full bg-white text-black rounded relative"
        >
          <select class="py-2 pr-8 px-4 appearance-none w-full" name="" id="">
            <option value="all">140 cm</option>
          </select>
          <div
            class="pointer-events-none absolute inset-y-0 right-2 flex items-center"
          >
            <svg
              class="w-4 h-4 text-gray-500"
              viewBox="0 0 20 20"
              fill="currentColor"
            >
              <path
                fill-rule="evenodd"
                d="M5.23 7.21a.75.75 0 011.06.02L10 11.172l3.71-3.94a.75.75 0 111.08 1.04l-4.25 4.5a.75.75 0 01-1.08 0l-4.25-4.5a.75.75 0 01.02-1.06z"
                clip-rule="evenodd"
              />
            </svg>
          </div>
        </div>
      </div>
      <div class="flex flex-col w-full">
        <label class="font-bold text-gray-600 text-sm" for="">Szerokość</label>
        <div
          class="flex justify-between items-center w-full bg-white text-black rounded relative"
        >
          <select class="py-2 pr-8 px-4 appearance-none w-full" name="" id="">
            <option value="all">200 cm</option>
          </select>
          <div
            class="pointer-events-none absolute inset-y-0 right-2 flex items-center"
          >
            <svg
              class="w-4 h-4 text-gray-500"
              viewBox="0 0 20 20"
              fill="currentColor"
            >
              <path
                fill-rule="evenodd"
                d="M5.23 7.21a.75.75 0 011.06.02L10 11.172l3.71-3.94a.75.75 0 111.08 1.04l-4.25 4.5a.75.75 0 01-1.08 0l-4.25-4.5a.75.75 0 01.02-1.06z"
                clip-rule="evenodd"
              />
            </svg>
          </div>
        </div>
      </div>
    </div>
    <button
      class="py-2 px-8 font-medium cursor-pointer bg-green-600 text-white w-full text-center"
    >
      Dodaj do koszyka
    </button>
  </div>
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
