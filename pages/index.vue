<template>
  <div class="relative flex flex-col min-h-screen text-gray-800">
    <!-- Background image + overlay clair -->
    <div
      class="absolute inset-0 bg-cover bg-center"
      style="background-image: url('https://previews.123rf.com/images/chzu/chzu2103/chzu210300003/165349205-falafel-houmous-pita-sur-fond-de-b%C3%A9ton-vue-d-en-haut-mise-au-point-s%C3%A9lective.jpg')"
    >
      <div class="absolute inset-0 bg-white/60"></div>
    </div>

    <!-- Contenu -->
    <div class="relative z-10 flex flex-col min-h-screen">
      <Header />

      <div class="sticky top-0 z-50 bg-white/80 backdrop-blur shadow-md">
        <MenuTabs :categories="categories" @selectCategory="selected = $event" />
      </div>

      <main class="flex-grow p-4 max-w-5xl mx-auto space-y-12">
        <MenuSection
          v-for="cat in filteredCategories"
          :key="cat.name"
          :title="cat.name"
          :items="cat.items"
        />
      </main>

      <Footer />
    </div>
  </div>
</template>

<script setup>
import Header from '~/components/Header.vue'
import Footer from '~/components/Footer.vue'
import MenuTabs from '~/components/MenuTabs.vue'
import MenuSection from '~/components/MenuSection.vue'

const selected = ref('Pita')

const categories = [
  {
    name: 'Pita',
    items: [
      {
        name: 'Pita Falafel',
        desc: 'Pita garnie de falafel, houmous, légumes frais',
        price: '7 €',
        img: 'https://pngimg.com/d/falafel_PNG18.png',
      },
      {
        name: 'Pita Shawarma',
        desc: 'Pita garnie de shawarma de poulet, sauce tahini',
        price: '8 €',
        img: 'https://131670744.cdn6.editmysite.com/uploads/1/3/1/6/131670744/73LZTFNOVYQ3RQK223BZC3EU.jpeg?width=2400&optimize=medium',
      },
      {
        name: 'Pita Veggie',
        desc: 'Pita avec légumes grillés et sauce yaourt',
        price: '6 €',
        img: 'https://boustan.ca/wp-content/uploads/2023/11/boustan-lebanese-restaurant-beef-shawarma-pita.png',
      },
    ],
  },
  {
    name: 'Falafel',
    items: [
      {
        name: 'Falafel Assiette',
        desc: 'Falafels servis avec houmous et salade',
        price: '9 €',
        img: 'https://www.academiedugout.fr/images/50789/1200-686/10023-nigiri-sushi.jpg?poix=50&poiy=50',
      },
      {
        name: 'Falafel Sandwich',
        desc: 'Sandwich pita falafel avec sauce piquante',
        price: '7 €',
        img: 'https://lady-sushi.fr/app/uploads/2023/09/image-scaled-1-960x646.jpg',
      },
    ],
  },
  {
    name: 'Shawarma',
    items: [
      {
        name: 'Shawarma Poulet',
        desc: 'Shawarma de poulet mariné avec légumes frais',
        price: '8 €',
        img: 'https://miyakosushi.fr/wp-content/uploads/2024/05/MENU-SUSHI-UNE.png',
      },
      {
        name: 'Shawarma Agneau',
        desc: 'Shawarma d’agneau, pita et sauce maison',
        price: '10 €',
        img: 'https://files.gandi.ws/gandi43264/image/m11.jpg',
      },
      {
        name: 'Shawarma Mixte',
        desc: 'Mix poulet et agneau avec sauce à l’ail',
        price: '12 €',
        img: 'https://sushishop.com/wp-content/uploads/2024/12/SS24_UEATS_CHU_SALMON.jpg',
      },
    ],
  },
]

const filteredCategories = computed(() =>
  categories.filter((c) => c.name === selected.value)
)
</script>
