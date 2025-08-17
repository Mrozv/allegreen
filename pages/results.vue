<template>
  <div class="bg-blue-50 flex flex-col items-center">
    <main
      class="align-middle flex p-4 py-16 text-black gap-4 min-h-screen w-full max-w-[1200px] max-sm:flex-col"
    >
      <Filters></Filters>
      <div class="w-full flex flex-col gap-4">
        <h1 class="text-2xl font-bold">
          Wyniki wyszukiwania dla: "Materac 140x200"
        </h1>
        <ResultCard
          id="1"
          title="Materac kieszeniowy 140x200"
          description="Wygodny, elegancki materac najwyższej jakości."
          price="599"
          image-url="mat1.jpg"
        ></ResultCard>
        <ResultCard
          id="2"
          title="Materac sprężynowy 140x200"
          description="Ekologiczny materac wytworzony z naturalnych materiałów."
          price="999"
          image-url="mat2.jpg"
        ></ResultCard>
        <ResultCard
          id="3"
          title="Materac kokosowy 140x200"
          description="Wykonany z miękkiego materiału. Idealnie dopasowuje się do kręgosłupa."
          price="899"
          image-url="mat3.jpg"
        ></ResultCard>
      </div>
    </main>
  </div>
</template>

<script setup></script>
