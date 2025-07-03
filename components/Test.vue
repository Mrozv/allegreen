<template>
  <button @click="increment">kliknieto: {{ count }}</button>
  <ul v-show="count % 2 === 0">
    <li>Adam</li>
    <li>Jan</li>
    <li>Jakub</li>
    <li>Ania</li>
    <li>Natalia</li>
  </ul>
  <ul v-if="count % 2 === 0">
    <li>Adam</li>
    <li>Jan</li>
    <li>Jakub</li>
    <li>Ania</li>
    <li>Natalia</li>
  </ul>
</template>

<script lang="ts" setup>
const count = ref(0);

const increment = () => {
  count.value++;
};
</script>
