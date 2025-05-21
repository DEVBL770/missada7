<template>
  <div class="relative flex flex-col min-h-screen text-gray-800">
    <!-- Image de fond avec filtre gris clair -->
    <div 
      class="absolute inset-0 bg-cover bg-center" 
      style="background-image: url('https://images.unsplash.com/photo-1600891964599-f61ba0e24092')"
    >
      <div class="absolute inset-0 bg-gray-100/35"></div>  <!-- overlay gris clair à 20% d'opacité -->
    </div>

    <!-- Contenu au-dessus -->
    <div class="relative flex flex-col min-h-screen">
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
const selected = ref('Antipasti')

const categories = [
  {
    name: 'Antipasti',
    items: [
      { name: 'Bruschetta', desc: 'Pain grillé, tomates fraîches, basilic', price: '6 €', img: 'https://img.freepik.com/photos-gratuite/assiette-gros-plan-sushi_23-2148631177.jpg?auto=compress&cs=tinysrgb&w=600' },
      { name: 'Mozzarella Sticks', desc: 'Mozzarella panée, sauce tomate maison', price: '7 €', img: 'https://st4.depositphotos.com/19157714/31390/i/450/depositphotos_313903296-stock-photo-close-view-delicious-sushi-set.jpg' },
      { name: 'Arancini', desc: 'Boulettes de riz farcies, panées et frites', price: '7 €', img: 'https://img.freepik.com/photos-premium/arancini-italiens-traditionnels-riz-boulettes-sauce_90220-1229.jpg' },
    ],
  },
  {
    name: 'Pizzas',
    items: [
      { name: 'Margherita', desc: 'Tomate, mozzarella, basilic', price: '10 €', img: 'https://miyakosushi.fr/wp-content/uploads/2024/05/MENU-SUSHI-UNE.png' },
      { name: 'Regina', desc: 'Jambon, champignons, mozzarella', price: '12 €', img: 'https://files.gandi.ws/gandi43264/image/m11.jpg' },
      { name: '4 Fromaggi', desc: 'Mozzarella, gorgonzola, parmesan, chèvre', price: '13 €', img: 'https://img.freepik.com/photos-gratuite/pizza-quatre-fromages-table-bois_23-2148359203.jpg' },
    ],
  },
  {
    name: 'Pâtes',
    items: [
      { name: 'Spaghetti Carbonara', desc: 'Crème, œuf, pancetta, parmesan', price: '11 €', img: 'https://img.freepik.com/photos-gratuite/spaghetti-carbonara-cremeux-parmesan_140725-3905.jpg' },
      { name: 'Penne Arrabiata', desc: 'Sauce tomate épicée, ail, basilic', price: '10 €', img: 'https://img.freepik.com/photos-gratuite/penne-arrabiata-pates-epicees_140725-9187.jpg' },
    ],
  },
  {
    name: 'Desserts',
    items: [
      { name: 'Tiramisu', desc: 'Café, mascarpone, cacao', price: '6 €', img: 'https://sushishop.com/wp-content/uploads/2024/12/SS24_UEATS_CHU_SALMON.jpg' },
      { name: 'Panna Cotta', desc: 'Crème cuite, coulis de fruits rouges', price: '5 €', img: 'https://img.freepik.com/photos-gratuite/panna-cotta-fraises_144627-8018.jpg' },
      { name: 'Cannoli', desc: 'Pâtisserie fourrée à la ricotta sucrée', price: '4 €', img: 'https://img.freepik.com/photos-premium/cannoli-dessert-italien-traditionnel-ricotta-chocolat_90220-1242.jpg' },
    ],
  },
  {
    name: 'Boissons',
    items: [
      { name: 'Eau Minérale', desc: 'Plate ou gazeuse', price: '2 €', img: 'https://img.freepik.com/photos-gratuite/verre-eau-froide-table_1150-38357.jpg' },
      { name: 'Sodas', desc: 'Coca, Fanta, Sprite', price: '3 €', img: 'https://img.freepik.com/photos-gratuite/verre-coca-glacons_144627-16227.jpg' },
      { name: 'Vins Italiens', desc: 'Rouge, Blanc, Rosé (verre)', price: '5 €', img: 'https://img.freepik.com/photos-gratuite/verre-vin-rouge-table_144627-24272.jpg' },
    ],
  },
]

const filteredCategories = computed(() => categories.filter(c => c.name === selected.value))
</script>