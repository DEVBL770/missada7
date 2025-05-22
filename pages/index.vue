<template>
  <div class="flex flex-col min-h-screen relative">
    <div class="absolute inset-0 z-0">
      <div class="w-full h-full bg-[url('https://images.unsplash.com/photo-1625943477729-d59f9d22bfb5')] bg-cover bg-center">
        <div class="w-full h-full bg-white/30 backdrop-brightness-90"></div>
      </div>
    </div>

    <div class="relative z-10 flex flex-col min-h-screen">
      <Header />

      <main class="flex-grow">
        <div class="sticky top-0 z-50 bg-white/80 backdrop-blur shadow-md">
          <MenuTabs :categories="categories" @selectCategory="selected = $event" />
        </div>

        <div class="p-4 max-w-4xl mx-auto space-y-10">
          <MenuSection
            v-for="cat in filteredCategories"
            :key="cat.name"
            :title="cat.name"
            :items="cat.items"
          />
        </div>
      </main>

      <Footer />
    </div>
  </div>
</template>

<script setup>
const selected = ref('Pitas')

const categories = [
  {
    name: 'Pitas',
    items: [
      { name: 'Shawarma', desc: 'Émincé de dinde grillée, salade, tahini', price: '9€', img: 'https://cdn.pixabay.com/photo/2017/01/04/13/58/shawarma-1952794_1280.jpg' },
      { name: 'Falafel', desc: 'Boulettes de pois chiches frites, salade, tahini', price: '8€', img: 'https://cdn.pixabay.com/photo/2020/11/10/14/38/falafel-5731621_1280.jpg' },
    ],
  },
  {
    name: 'Assiettes',
    items: [
      { name: 'Assiette Shawarma', desc: 'Viande, riz, salades, pain pita', price: '12€', img: 'https://cdn.pixabay.com/photo/2017/06/27/08/56/shawarma-2442996_1280.jpg' },
      { name: 'Assiette Falafel', desc: 'Falafels, houmous, salades, pain pita', price: '11€', img: 'https://cdn.pixabay.com/photo/2017/05/07/08/56/falafel-2290741_1280.jpg' },
    ],
  },
  {
    name: 'Desserts',
    items: [
      { name: 'Baklava', desc: 'Pâtisserie au miel et noix', price: '4€', img: 'https://cdn.pixabay.com/photo/2020/02/02/18/24/baklava-4813868_1280.jpg' },
      { name: 'Malabi', desc: 'Crème à la rose, pistaches', price: '4€', img: 'https://cdn.pixabay.com/photo/2022/08/11/10/25/malabi-7378552_1280.jpg' },
    ],
  },
  {
    name: 'Boissons',
    items: [
      { name: 'Limonana', desc: 'Citronnade à la menthe fraîche', price: '3€', img: 'https://cdn.pixabay.com/photo/2015/07/02/10/18/lemonade-828974_1280.jpg' },
      { name: 'Bière Maccabee', desc: 'Bière israélienne', price: '4€', img: 'https://cdn.pixabay.com/photo/2015/11/19/21/11/beer-1058087_1280.jpg' },
    ],
  },
]

const filteredCategories = computed(() => categories.filter(c => c.name === selected.value))
</script>
