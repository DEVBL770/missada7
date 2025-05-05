<template>
  <div class="max-w-2xl mx-auto px-4 py-8">
    <Header />
    <MenuSection title="Entrées" :items="menu.entrees" />
    <MenuSection title="Plats" :items="menu.plats" />
    <MenuSection title="Desserts" :items="menu.desserts" />
    <MenuSection title="Boissons" :items="menu.boissons" />
    <Footer />
  </div>
</template>

<script setup>
import Header from '@/components/Header.vue'
import MenuSection from '@/components/MenuSection.vue'
import Footer from '@/components/Footer.vue'

const menu = {
  entrees: [
    { name: 'Tartare de thon rouge', description: 'Mangue, citron vert, coriandre fraîche', price: 18 },
    { name: 'Foie gras maison', description: 'Gelée de Sauternes, pain brioché', price: 22 },
    { name: 'Velouté de potimarron', description: 'Crème de châtaigne, éclats de noisettes', price: 14 },
    { name: 'Carpaccio de Saint-Jacques', description: 'Huile de truffe, citron caviar', price: 20 },
  ],
  plats: [
    { name: 'Filet de bar rôti', description: 'Purée de céleri, émulsion au champagne', price: 32 },
    { name: 'Magret de canard', description: 'Réduction balsamique, légumes glacés', price: 29 },
    { name: 'Risotto aux morilles', description: 'Parmesan affiné 24 mois, huile de truffe', price: 28 },
    { name: 'Tournedos de boeuf', description: 'Sauce foie gras, gratin dauphinois', price: 36 },
  ],
  desserts: [
    { name: 'Fondant au chocolat', description: 'Chocolat grand cru 70%, glace vanille', price: 12 },
    { name: 'Tartelette au citron meringuée', description: 'Meringue italienne, pâte sablée', price: 11 },
    { name: 'Assiette de fromages affinés', description: 'Sélection de la maison Barthélemy', price: 14 },
    { name: 'Pavlova aux fruits rouges', description: 'Crème chantilly maison, fruits frais', price: 13 },
  ],
  boissons: [
    { name: 'Verre de vin rouge — Saint-Émilion', description: 'Château Bellefont-Belcier 2020', price: 10 },
    { name: 'Verre de vin blanc — Sancerre', description: 'Domaine Vacheron 2021', price: 9 },
    { name: 'Champagne brut — Ruinart', description: 'Flûte 12cl', price: 14 },
    { name: 'Eau minérale plate', description: 'Evian 50cl', price: 4 },
    { name: 'Eau pétillante', description: 'San Pellegrino 50cl', price: 5 },
    { name: 'Café expresso', description: 'Café arabica pur origine', price: 3.5 },
  ]
}
</script>
