<template>
  <li class="flex shadow-xl bg-white rounded max-sm:flex-col overflow-hidden">
    <div class="h-full w-48 max-sm:w-full bg-cover bg-center shrink-0">
      <img
        :src="imgSrc"
        :alt="title"
        class="w-full h-full object-cover"
        @error="onImgError"
      />
    </div>
    <div class="p-4 flex flex-col gap-2 w-full">
      <NuxtLink
        class="font-bold text-xl text-gray-600"
        :to="{
          path: `/products/${id}`,
          query: { title, description, price, imageUrl },
        }"
      >
        {{ title }}
      </NuxtLink>
      <p class="text-gray-400 text-sm">{{ description }}</p>
      <span class="text-green-600 font-semibold">
        {{ price.toFixed(2) }} zł
      </span>
      <NuxtLink
        class="py-2 px-8 font-medium cursor-pointer bg-green-600 text-white w-fit"
        :to="{
          path: `/cart`,
          query: { title, description, price, imageUrl },
        }"
      >
        Dodaj do koszyka
      </NuxtLink>
    </div>
  </li>
</template>

<script setup>
const props = defineProps({
  title: {
    type: String,
    default: "Nazwa produktu",
  },
  description: {
    type: String,
    default: "Opis produktu",
  },
  price: {
    type: [Number, String],
    default: "Cena produktu",
  },
  imageUrl: {
    type: Array,
  },
  id: {
    type: [Number, String],
    required: true,
  },
});

const fallbackImg = "/images/errorimg.jpg";
const imageSrc = computed(() => {
  return props.imageUrl && props.imageUrl[0] && props.imageUrl[0].small
    ? props.imageUrl[0].small
    : fallbackImg;
});
const imgSrc = ref(imageSrc.value);

watch(imageSrc, (val) => {
  imgSrc.value = val;
});

function onImgError() {
  imgSrc.value = fallbackImg;
}
</script>
