<script setup>
import { useRoute } from "vue-router";

const route = useRoute();
const { title, description, price, imageUrl, id } = route.query;
</script>

<template>
  <div class="bg-blue-50 flex flex-col items-center min-h-screen">
    <main class="flex p-4 py-16 gap-4 max-w-[1200px] h-full items-stretch">
      <Gallery
        :title="title"
        :description="description"
        :price="price"
        :image-url="imageUrl"
        :id="id"
      />
      <product-menu
        :title="title"
        :description="description"
        :price="price"
        :image-url="imageUrl"
        :id="id"
      ></product-menu>
    </main>
  </div>
</template>
