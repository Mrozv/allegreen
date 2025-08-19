<template>
  <div class="bg-blue-50 flex flex-col items-center">
    <main
      class="align-middle flex px-4 py-16 text-black gap-4 min-h-screen w-full max-w-[1200px] max-sm:flex-col"
    >
      <div class="flex flex-col gap-4 w-full">
        <h1 class="text-2xl font-bold">Twój koszyk</h1>
        <ul class="w-full flex flex-col gap-4">
          <CartCard
            v-for="item in cartItems"
            :key="item.id"
            :id="item.id"
            :title="item.title"
            :description="item.description"
            :price="item.price"
            :quantity="item.quantity"
            :image-url="item.imageUrl"
            :increaseQuantity="increaseQuantity"
            :decreaseQuantity="decreaseQuantity"
          ></CartCard>
        </ul>
      </div>
      <CartSummary :total="totalPrice"></CartSummary>
    </main>
  </div>
</template>

<script setup>
const cartItems = ref([
  {
    id: 1,
    title: "Materac kieszeniowy 140x200",
    description: "Wygodny, elegancki materac najwyższej jakości.",
    price: 599.0,
    quantity: 1,
    imageUrl: "mat1.jpg",
  },
  {
    id: 2,
    title: "Materac sprężynowy 140x200",
    description: "Ekologiczny materac wytworzony z naturalnych materiałów.",
    price: 999.99,
    quantity: 1,
    imageUrl: "mat2.jpg",
  },
  {
    id: 3,
    title: "Materac kokosowy 140x200",
    description:
      "Wykonany z miękkiego materiału. Idealnie dopasowuje się do kręgosłupa.",
    price: 899.0,
    quantity: 1,
    imageUrl: "mat3.jpg",
  },
]);

const increaseQuantity = (itemId) => {
  const cartItem = cartItems.value.find((i) => i.id === itemId);
  if (cartItem) {
    cartItem.quantity++;
  }
};

const decreaseQuantity = (itemId) => {
  const cartItem = cartItems.value.find((i) => i.id === itemId);
  if (cartItem && cartItem.quantity > 1) {
    cartItem.quantity--;
  }
};

const totalPrice = computed(() => {
  return cartItems.value.reduce((total, item) => {
    return total + item.price * item.quantity;
  }, 0);
});
</script>
