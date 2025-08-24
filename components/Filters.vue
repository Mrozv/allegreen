<template>
  <div
    class="bg-white p-4 h-fit rounded shadow-xl flex flex-col gap-4 sticky top-4 max-sm:static"
  >
    <h1 class="text-xl font-semibold">Filtry</h1>
    <!-- <div class="flex flex-col">
      <h2 class="font-semibold">Kategorie</h2>
      <button class="text-gray-600">Dom i ogród</button>
      <button class="text-gray-600">Sypialnia</button>
      <button class="text-gray-600">Materace</button>
      <button class="text-gray-600">Łóżka</button>
    </div> -->
    <div>
      <h2 class="font-semibold">Dostawa</h2>
      <div class="flex gap-2">
        <input type="checkbox" id="free_delivery" />
        <label for="free_delivery" class="text-gray-600">Darmowa dostawa</label>
      </div>
      <div class="flex gap-2">
        <input type="checkbox" id="delivery_till_thuesday" />
        <label for="delivery_till_thuesday" class="text-gray-600">
          Dostawa do wtorku
        </label>
      </div>
    </div>
    <div>
      <h2 class="font-semibold">Stan</h2>
      <div class="flex gap-2">
        <input type="checkbox" id="new" />
        <label for="new" class="text-gray-600">Nowe</label>
      </div>
      <div class="flex gap-2">
        <input type="checkbox" id="used" />
        <label for="used" class="text-gray-600">Używane</label>
      </div>
    </div>
    <div>
      <h2 class="font-semibold">Cena</h2>
      <input class="text-gray-600 p-2" type="number" placeholder="Od" />
    </div>
  </div>
</template>

<script setup></script>
