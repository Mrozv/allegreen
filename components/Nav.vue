<template>
  <div class="bg-green-600 flex justify-center align-middle">
    <div
      class="justify-between align-middle flex p-4 text-white gap-16 w-full max-w-[1200px]"
    >
      <span class="text-2xl font-bold">Allegreen</span>
      <div class="flex items-center gap-4 w-full">
        <div
          class="flex justify-between items-center w-full bg-white text-black rounded relative"
        >
          <input
            class="py-2 px-4 border-none w-full"
            type="text"
            placeholder="Czego szukasz?"
          />
          <select
            class="py-2 pr-8 px-4 appearance-none border-l-1 border-gray-200"
            name=""
            id=""
          >
            <option value="all">Wszystkie</option>
            <option value="electronics">Elektronika</option>
            <option value="fashion">Moda</option>
            <option value="home">Dom i ogród</option>
            <option value="toys">Zabawki</option>
            <option value="books">Książki</option>
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
        <button class="font-medium cursor-pointer">SZUKAJ</button>
      </div>
      <div class="flex items-center">
        <ul class="flex gap-8 text-3xl">
          <li>
            <NuxtLink class="flex" to="/">
              <span class="material-symbols-outlined">home</span>
            </NuxtLink>
          </li>
          <li>
            <NuxtLink class="flex" to="/categories">
              <span class="material-symbols-outlined">interests</span>
            </NuxtLink>
          </li>
          <li>
            <NuxtLink class="flex" to="/discounts">
              <span class="material-symbols-outlined">sell</span>
            </NuxtLink>
          </li>
          <li>
            <NuxtLink class="flex" to="/contact">
              <span class="material-symbols-outlined">
                connect_without_contact
              </span>
            </NuxtLink>
          </li>
        </ul>
      </div>
    </div>
  </div>
</template>

<script setup></script>

<style scoped></style>
