<template>
  <div
    v-if="modalValue"
    class="fixed inset-0 bg-gray-800/50 flex items-center justify-center z-50"
  >
    <div class="bg-white rounded-lg shadow-lg p-6 max-w-md w-full">
      <h2 class="text-xl font-semibold mb-4">Modal Title</h2>
      <p class="mb-4">This is a modal dialog. Hi {{ userName }}</p>
      <button
        @click="close"
        class="bg-blue-500 text-white px-4 py-2 rounded hover:bg-blue-600"
      >
        Close
      </button>
    </div>
  </div>
</template>

<script setup>
const props = defineProps({
  modalValue: {
    type: Boolean,
    required: true,
    default: false,
  },

  userName: {
    type: String,
  },
});
const emit = defineEmits(["update:modalValue"]);
const close = () => {
  emit("modalValue", false);
};
</script>
