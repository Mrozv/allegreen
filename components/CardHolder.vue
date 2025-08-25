<template>
  <div class="flex justify-center align-middle">
    <div
      class="align-middle items-center flex flex-col p-4 text-black gap-4 max-w-[1200px] w-full max-sm:gap-0"
    >
      <h1
        :class="[
          'font-bold text-2xl',
          section === 'second' ? 'w-full' : 'max-sm:w-full',
        ]"
      >
        {{ title }}
      </h1>
      <ul
        class="flex justify-between gap-4 w-full max-sm:overflow-auto max-sm:py-8 max-sm:px-4"
      >
        <PopularCard
          v-if="section === 'first'"
          v-for="(card, idx) in cards"
          :key="idx"
          :title="card.title"
          :description="card.description"
          :price="card.price"
          :image-url="card.imageUrl[0].small"
        />
        <SmallCard
          v-if="section === 'second'"
          v-for="(card, idx) in cards"
          :key="idx"
          :title="card.title"
          :price="card.price"
          :image-url="card.imageUrl[0].small"
        />
      </ul>
    </div>
  </div>
</template>

<script setup>
const props = defineProps({
  title: {
    type: String,
    default: "Produkty",
  },
  cards: {
    type: Array,
    default: () => [],
  },
  section: {
    type: String,
  },
});
</script>

<style scoped></style>
