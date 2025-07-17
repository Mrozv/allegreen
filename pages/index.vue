<template>
  <Nav></Nav>
  <Hero></Hero>
  <main class="flex flex-col gap-4">
    <CardHolder
      section="first"
      title="Popularne produkty"
      :cards="[
        {
          title: 'Drzewo oliwne',
          description: 'Oliwka z regionu Morza Śródziemnego',
          price: 29.99,
          imageUrl: 'fatih-berat-orer-oajlEpl_m_w-unsplash.jpg',
        },
        {
          title: 'Szafka z drewna',
          description: 'Ręcznie robiona szafka z lokalnego drewna',
          price: 31.99,
          imageUrl: 'forlll-de-rad-L7_U32YYN24-unsplash.jpg',
        },
        {
          title: 'Zeszyt notes',
          description: 'Ekologiczny zeszyt z recyklingu',
          price: 224.99,
          imageUrl: 'kelly-sikkema-gRZynBXSdz4-unsplash.jpg',
        },
        {
          title: 'Rower górski',
          description: 'Rower górski z aluminium',
          price: 99.99,
          imageUrl: 'logan-weaver-lgnwvr-LMCp7fexTjQ-unsplash.jpg',
        },
      ]"
    ></CardHolder>
    <CardHolder
      section="second"
      title="Wnętrze w pięknym stylu"
      :cards="[
        {
          title: 'Latawiec z naturalnych materiałów',
          price: 39.99,
          imageUrl: 'zd1.jpg',
        },
        {
          title: 'Telefon Akami 8 generacji',
          price: 779.99,
          imageUrl: 'zd2.jpg',
        },
        {
          title: 'Plakat Mercedes-Benz EQA',
          price: 49.99,
          imageUrl: 'zd3.jpg',
        },
        {
          title: 'Deska surfingowa z drewna bambusowego',
          price: 199.99,
          imageUrl: 'zd4.jpg',
        },
        {
          title: 'Suknia czerwona z naturalnych włókien',
          price: 299.99,
          imageUrl: 'zd5.jpg',
        },
        {
          title: 'Obraz olejny na płótnie',
          price: 89.99,
          imageUrl: 'zd6.jpg',
        },
      ]"
    ></CardHolder>
  </main>
</template>

<script setup></script>
