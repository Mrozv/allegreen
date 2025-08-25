<template>
  <Hero></Hero>
  <main class="flex flex-col gap-4 min-h-screen bg-blue-50">
    <CardHolder
      section="first"
      title="Popularne produkty"
      :cards="[products[0], products[1], products[2], products[3]]"
    ></CardHolder>
    <CardHolder
      section="second"
      title="Wnętrze w pięknym stylu"
      :cards="[
        products[4],
        products[5],
        products[6],
        products[7],
        products[8],
        products[9],
      ]"
    ></CardHolder>
  </main>
</template>

<script setup>
const { data: products } = useLazyFetch("/api/products", {
  lazy: true,
});

console.log(products);
</script>
