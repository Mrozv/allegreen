<template>
  <div
    class="bg-white w-3/10 p-4 h-fit rounded shadow-xl flex flex-col gap-4 max-sm:w-full"
  >
    <h1 class="text-xl font-semibold">Podsumowanie</h1>
    <div class="border-b pb-2">
      <div class="flex justify-between">
        <h2 class="font-regular">Wartość produktów:</h2>
        <h2 class="font-regular">{{ total.toFixed(2) }} zł</h2>
      </div>
      <div class="flex justify-between">
        <h2 class="font-regular">Dostawa:</h2>
        <h2 class="font-regular text-green-600">0,00 zł</h2>
      </div>
    </div>
    <div class="flex justify-between">
      <h2 class="font-semibold">Razem:</h2>
      <h2 class="font-semibold">{{ total.toFixed(2) }} zł</h2>
    </div>
    <div class="flex flex-col align-middle items-center gap-2">
      <NuxtLink
        class="py-2 px-8 w-full text-center font-medium cursor-pointer bg-green-600 text-white"
        :to="{
          path: `/cart`,
        }"
      >
        Dostawa i płatność
      </NuxtLink>
      <button class="text-green-600 cursor-pointer">Kontynuuj zakupy</button>
    </div>
  </div>
</template>

<script setup>
const props = defineProps({
  total: {
    type: Number,
    default: 0,
  },
});
</script>
