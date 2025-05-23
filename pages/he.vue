<template>
  <div dir="rtl" class="relative flex flex-col min-h-screen text-gray-800">
    <!-- Background + overlay -->
    <div
      class="absolute inset-0 bg-cover bg-center"
      style="background-image: url('https://previews.123rf.com/images/chzu/chzu2103/chzu210300003/165349205-falafel-houmous-pita-sur-fond-de-b%C3%A9ton-vue-d-en-haut-mise-au-point-s%C3%A9lective.jpg')"
    >
      <div class="absolute inset-0 bg-white/60"></div>
    </div>

    <!-- Contenu -->
    <div class="relative z-10 flex flex-col min-h-screen">
      <HeaderHe />

      <div class="sticky top-0 z-50 bg-white/80 backdrop-blur shadow-md">
        <MenuTabsHe :categories="categories" @selectCategory="selected = $event" />
      </div>

      <main class="flex-grow p-4 max-w-5xl mx-auto space-y-12">
        <MenuSectionHe
          v-for="cat in filteredCategories"
          :key="cat.name"
          :title="cat.name"
          :items="cat.items"
        />
      </main>

      <FooterHe />
    </div>
  </div>
</template>

<script setup>
import HeaderHe from '~/components/HeaderHe.vue'
import FooterHe from '~/components/FooterHe.vue'
import MenuTabsHe from '~/components/MenuTabsHe.vue'
import MenuSectionHe from '~/components/MenuSectionHe.vue'

const selected = ref('פיתה') // "Pita" en hébreu

const categories = [
  {
    name: 'פיתה',
    items: [
      {
        name: 'פיתה פלאפל',
        desc: 'פיתה ממולאת בפלאפל, חומוס וירקות טריים',
        price: '₪28',
        img: 'https://img.freepik.com/photos-gratuite/assiette-gros-plan-sushi_23-2148631177.jpg?semt=ais_hybrid&w=740',
      },
      {
        name: 'פיתה שווארמה',
        desc: 'פיתה עם שווארמת עוף ורוטב טחינה',
        price: '₪30',
        img: 'https://st4.depositphotos.com/19157714/31390/i/450/depositphotos_313903296-stock-photo-close-view-delicious-sushi-set.jpg',
      },
      {
        name: 'פיתה ויגי',
        desc: 'פיתה עם ירקות קלויים ורוטב יוגורט',
        price: '₪25',
        img: 'https://www.kikkoman.fr/fileadmin/processed/a/d/csm_945-recipe-page-gunkan-maki-sushi-with-prawn-cucumber_desktop_f5c8020ef0.jpg',
      },
    ],
  },
  {
    name: 'פלאפל',
    items: [
      {
        name: 'מגש פלאפל',
        desc: 'כדורי פלאפל עם חומוס וסלט',
        price: '₪35',
        img: 'https://www.academiedugout.fr/images/50789/1200-686/10023-nigiri-sushi.jpg?poix=50&poiy=50',
      },
      {
        name: 'סנדוויץ\' פלאפל',
        desc: 'סנדוויץ\' פיתה עם פלאפל ורוטב חריף',
        price: '₪28',
        img: 'https://lady-sushi.fr/app/uploads/2023/09/image-scaled-1-960x646.jpg',
      },
    ],
  },
  {
    name: 'שווארמה',
    items: [
      {
        name: 'שווארמת עוף',
        desc: 'שווארמת עוף עם ירקות טריים',
        price: '₪30',
        img: 'https://miyakosushi.fr/wp-content/uploads/2024/05/MENU-SUSHI-UNE.png',
      },
      {
        name: 'שווארמת כבש',
        desc: 'שווארמת כבש עם פיתה ורוטב ביתי',
        price: '₪38',
        img: 'https://files.gandi.ws/gandi43264/image/m11.jpg',
      },
      {
        name: 'שווארמה מעורבת',
        desc: 'תערובת עוף וכבש עם רוטב שום',
        price: '₪42',
        img: 'https://sushishop.com/wp-content/uploads/2024/12/SS24_UEATS_CHU_SALMON.jpg',
      },
    ],
  },
]

const filteredCategories = computed(() =>
  categories.filter((c) => c.name === selected.value)
)
</script>
