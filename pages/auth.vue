<template>
  <main class="flex gap-4 min-h-screen bg-blue-50 items-center justify-center">
    <div class="flex gap-4 max-w-[1200px] w-full max-sm:flex-col max-sm:mx-2">
      <form
        action=""
        class="bg-white p-4 rounded shadow-xl flex flex-col gap-4 h-full w-full max-sm:flex-col"
      >
        <div
          class="flex gap-2 text-green-600 text-2xl items-center font-semibold"
        >
          <span class="material-symbols-outlined">login</span>
          <h1>Zaloguj się</h1>
        </div>
        <input
          class="border-1 border-slate-400 rounded py-2 px-4"
          type="text"
          placeholder="Login"
        />
        <input
          class="border-1 border-slate-400 rounded py-2 px-4"
          type="password"
          placeholder="Hasło"
        />
        <button
          class="py-2 px-8 font-medium cursor-pointer bg-green-600 text-white w-full"
        >
          Zaloguj się
        </button>
      </form>

      <form
        action=""
        class="bg-white p-4 rounded shadow-xl flex flex-col gap-4 h-full w-full"
      >
        <div
          class="flex gap-2 text-green-600 text-2xl items-center font-semibold"
        >
          <span class="material-symbols-outlined">person_add</span>
          <h1>Zarejestruj się</h1>
        </div>
        <input
          class="border-1 border-slate-400 rounded py-2 px-4"
          type="text"
          placeholder="Imię"
        />
        <input
          class="border-1 border-slate-400 rounded py-2 px-4"
          type="text"
          placeholder="Nazwisko"
        />
        <input
          class="border-1 border-slate-400 rounded py-2 px-4"
          type="email"
          placeholder="E-mail"
        />
        <input
          class="border-1 border-slate-400 rounded py-2 px-4"
          type="password"
          placeholder="Hasło"
        />
        <button
          class="py-2 px-8 font-medium cursor-pointer bg-green-600 text-white w-full"
        >
          Zarejestruj się
        </button>
      </form>
    </div>
  </main>
</template>

<script setup>
definePageMeta({ layout: "auth-lo" });
</script>
