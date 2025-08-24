<template>
  <div
    class="bg-white p-4 h-fit rounded shadow-xl flex flex-col gap-4 sticky top-4 max-sm:static"
  >
    <h1 class="text-xl font-semibold">Filtry</h1>
    <div>
      <h2 class="font-semibold">Dostawa</h2>
      <div class="flex gap-2">
        <input
          type="checkbox"
          @click="
            () => {
              free_delivery = !free_delivery;
              toggleCheckBox();
            }
          "
          id="free_delivery"
        />
        <label for="free_delivery" class="text-gray-600">Darmowa dostawa</label>
      </div>
      <div class="flex gap-2">
        <input
          type="checkbox"
          @click="
            () => {
              delivery_till_thuesday = !delivery_till_thuesday;
              toggleCheckBox();
            }
          "
          id="delivery_till_thuesday"
        />
        <label for="delivery_till_thuesday" class="text-gray-600">
          Dostawa do wtorku
        </label>
      </div>
    </div>
    <div>
      <h2 class="font-semibold">Stan</h2>
      <div class="flex gap-2">
        <input
          type="checkbox"
          @click="
            () => {
              new_item = !new_item;
              toggleCheckBox();
            }
          "
          id="new"
          value="new"
        />
        <label for="new" class="text-gray-600">Nowe</label>
      </div>
      <div class="flex gap-2">
        <input
          type="checkbox"
          @click="
            () => {
              used = !used;
              toggleCheckBox();
            }
          "
          id="used"
          value="used"
        />
        <label for="used" class="text-gray-600">Używane</label>
      </div>
    </div>
    <div>
      <h2 class="font-semibold">Cena</h2>
      <input class="text-gray-600 p-2" type="number" placeholder="Od" />
    </div>
  </div>
</template>

<script setup>
const free_delivery = ref(false);
const delivery_till_thuesday = ref(false);
const new_item = ref(false);
const used = ref(false);

const checkBoxes = ref({
  free_delivery: free_delivery,
  delivery_till_thuesday: delivery_till_thuesday,
  new: new_item,
  used: used,
});

const emit = defineEmits(["update:filters"]);

function toggleCheckBox() {
  emit("update:filters", { ...checkBoxes.value });
}
</script>
