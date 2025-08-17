<template>
  <div
    class="cookieComponent fixed bottom-0 left-0 w-full bg-white p-4 flex items-center justify-center shadow-lg z-50 border-t-2 border-green-600"
    v-if="cookiesVisible"
  >
    <div
      class="max-w-[1200px] w-full flex items-center justify-between gap-4 max-sm:flex-col"
    >
      <div class="flex gap-2">
        <div class="text-4xl">
          <span class="material-symbols-outlined text-green-600">cookie</span>
        </div>
        <p>
          Ta strona używa plików cookie, aby poprawić Twoje doświadczenia.
          Kontynuując korzystanie ze strony, zgadzasz się na użycie plików
          cookie.
        </p>
      </div>
      <div class="flex gap-2 max-sm:w-full">
        <button
          class="py-2 px-8 font-medium cursor-pointer bg-green-600 text-white w-fit max-sm:w-full"
          @click="acceptCookies"
        >
          Akceptuj
        </button>
        <button
          class="py-2 px-8 font-medium cursor-pointer bg-gray-400 text-white w-fit max-sm:w-full"
        >
          Odrzuć
        </button>
      </div>
    </div>
  </div>
</template>

<script setup>
const cookiesVisible = ref(false);

function checkCookies() {
  if (getCookie()) {
    cookiesVisible.value = false;
    return false;
  } else {
    cookiesVisible.value = true;
    return true;
  }
}
function acceptCookies() {
  setCookie(true);
  cookiesVisible.value = false;
}
function getCookie() {
  return useCookie("cookiesAccepted").value;
}

function setCookie(value) {
  const cookie = useCookie("cookiesAccepted");
  cookie.value = value;
}

onMounted(() => {
  checkCookies();
});
</script>
