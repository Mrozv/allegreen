<template>
  <div class="bg-blue-50 flex flex-col items-center">
    <main
      class="align-middle flex p-4 py-16 text-black gap-4 min-h-screen w-full max-w-[1200px] max-sm:flex-col"
    >
      <Filters></Filters>
      <div class="w-full flex flex-col gap-4">
        <h1 class="text-2xl font-bold" v-if="pending">
          Ładowanie produktów...
        </h1>
        <h1 class="text-2xl font-bold" v-if="!pending">Lista produktów</h1>

        <ResultCard
          v-for="product in products"
          :key="product.id"
          :id="product.id"
          :title="product.title"
          :description="product.description"
          :price="product.price"
          :image-url="product.imageUrl"
        ></ResultCard>
      </div>
    </main>
  </div>
</template>

<script setup>
const { data: products, pending } = useLazyFetch("/api/products", {
  lazy: true,
});
</script>
