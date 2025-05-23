<template>
  <div dir="rtl" class="bg-white p-4 rounded-lg shadow-md flex items-center gap-4">
    <!-- Prix à gauche -->
    <div class="text-yellow-600 font-bold ml-auto">{{ item.price }}</div>

    <!-- Texte centré, aligné à droite -->
    <div class="flex-1 text-right">
      <div class="font-bold text-lg">{{ item.name }}</div>
      <div class="text-sm text-gray-600">{{ item.desc }}</div>
    </div>

    <!-- Image à droite -->
    <img :src="item.img" :alt="item.name" class="w-20 h-20 object-contain rounded" />
  </div>
</template>

<script setup>
defineProps(['item'])
</script>
