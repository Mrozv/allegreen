<template>
  <Modal
    @modalValue="emitModalShow"
    :modal-value="showModal"
    :userName="'Łukasz'"
  />
  <button
    @click="emitModalShow"
    class="bg-blue-500 text-white px-4 py-2 rounded hover:bg-blue-600"
  >
    Open Modal
  </button>
</template>

<script setup>
const showModal = ref(false);

const emitModalShow = () => {
  showModal.value = !showModal.value;
};
</script>
