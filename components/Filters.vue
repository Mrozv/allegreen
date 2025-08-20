<template>
  <div
    class="bg-white p-4 h-fit rounded shadow-xl flex flex-col gap-4 sticky top-4 max-sm:static"
  >
    <h1 class="text-xl font-semibold">Filtry</h1>
    <div class="flex flex-col">
      <h2 class="font-semibold">Kategorie</h2>
      <span class="text-sm text-gray-600">Dom i ogród</span>
      <span class="text-sm text-gray-600">Sypialnia</span>
      <span class="text-sm text-gray-600">Materace</span>
      <span class="text-sm text-gray-600">Łóżka</span>
    </div>
    <div>
      <h2 class="font-semibold">Dostawa</h2>
      <div class="flex gap-2">
        <input type="checkbox" />
        <span class="text-sm text-gray-600">Darmowa dostawa</span>
      </div>
      <div class="flex gap-2">
        <input type="checkbox" />
        <span class="text-sm text-gray-600">Dostawa do wtorku</span>
      </div>
    </div>
    <div>
      <h2 class="font-semibold">Stan</h2>
      <div class="flex gap-2">
        <input type="checkbox" />
        <span class="text-sm text-gray-600">Nowe</span>
      </div>
      <div class="flex gap-2">
        <input type="checkbox" />
        <span class="text-sm text-gray-600">Używane</span>
      </div>
    </div>
    <div>
      <h2 class="font-semibold">Cena</h2>
      <input class="text-sm text-gray-600 p-2" type="number" placeholder="Od" />
    </div>
  </div>
</template>
