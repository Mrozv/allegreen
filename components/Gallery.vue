<template>
  <div class="w-3/4">
    <img @click="openModal" :src="`/images/${imageUrl}`" :alt="title" />
    <GalleryImgZoomModal
      v-if="viewModal"
      :imageUrl="imageUrl"
      v-on:closeModal="closeModal"
    ></GalleryImgZoomModal>
  </div>
</template>

<script setup>
const viewModal = ref(false);

function openModal() {
  viewModal.value = true;
}

function closeModal() {
  viewModal.value = false;
}

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
    type: String,
  },
  id: {
    type: [Number, String],
    required: true,
  },
});
</script>
