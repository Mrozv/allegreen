<template>
  <img
    class="fixed top-1/2 left-1/2 -translate-x-1/2 -translate-y-1/2 w-3/4 max-sm:w-full z-999"
    :src="`/images/${imageUrl}`"
    alt=""
  />
  <div
    @click="$emit('closeModal')"
    class="fixed top-0 left-0 w-full h-full z-998 bg-black/50"
  ></div>
</template>
<script setup>
const props = defineProps({
  imageUrl: {
    type: String,
    required: true,
  },
});
</script>
