<template>
  <li class="flex flex-col align-middle shadow-xl w-full max-sm:min-w-3/4">
    <img
      :src="imgSrc"
      :alt="title"
      class="w-full h-full object-cover"
      @error="onImgError"
    />
    <div class="p-4 flex flex-col gap-2">
      <h1 class="font-bold text-xl">{{ title }}</h1>
      <p class="text-gray-400 text-sm line-clamp-2">{{ description }}</p>
      <span class="text-green-600 font-semibold">{{ price }} zł</span>
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
    default: 0,
  },
  imageUrl: {
    type: String,
  },
});

const imgSrc = ref(props.imageUrl);

const fallbackImg = "/images/errorimg.jpg";
function onImgError() {
  imgSrc.value = fallbackImg;
}
</script>
