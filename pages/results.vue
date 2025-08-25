<template>
  <div class="bg-blue-50 flex flex-col items-center">
    <main
      class="align-middle flex p-4 py-16 text-black gap-4 min-h-screen w-full max-w-[1200px] max-sm:flex-col"
    >
      <Filters v-model:filters="filters" />

      <div class="w-full flex flex-col gap-4">
        <h1 class="text-2xl font-bold" v-if="pending">
          Ładowanie produktów...
        </h1>
        <h1 class="text-2xl font-bold" v-else>Lista produktów</h1>

        <ResultCard
          v-for="product in displayedItems"
          :key="product.id"
          :id="product.id"
          :title="product.title"
          :description="product.description"
          :price="product.price"
          :image-url="product.imageUrl"
        />
      </div>
    </main>
  </div>
</template>

<script setup>
const { data: products, pending } = useLazyFetch("/api/products", {
  lazy: true,
});

const itemsPerPage = 20;
const filters = ref({});

const filteredProducts = computed(() => {
  if (!products.value) return [];

  const noFilterActive = Object.values(filters.value).every(
    (v) => v === false || v === undefined
  );

  if (noFilterActive) {
    return products.value;
  }

  return products.value.filter((item) => {
    return (
      (filters.value.free_delivery && item.delivery_free) ||
      (filters.value.delivery_till_thuesday && item.delivery_till_thuesday) ||
      (filters.value.new && item.condition === "new") ||
      (filters.value.used && item.condition === "used")
    );
  });
});

const displayedItems = ref([]);

const loadMoreItems = () => {
  if (!filteredProducts.value) return;

  const start = displayedItems.value.length;
  const end = start + itemsPerPage;
  displayedItems.value.push(...filteredProducts.value.slice(start, end));
};

watch(filteredProducts, () => {
  displayedItems.value = [];
  loadMoreItems();
});

onMounted(() => {
  loadMoreItems();
  const sentinel = document.querySelector("#sentinel");

  const observer = new IntersectionObserver((entries) => {
    if (entries[0].isIntersecting) {
      loadMoreItems();
    }
  });
  observer.observe(sentinel);
});
</script>
