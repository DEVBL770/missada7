<template>
  <div class="bg-white p-4 rounded-lg shadow-md flex items-center gap-4">
    <img :src="item.img" :alt="item.name" class="w-20 h-20 object-contain" />
    <div class="flex-1">
      <div class="font-bold">{{ item.name }}</div>
      <div class="text-sm text-gray-600">{{ item.desc }}</div>
    </div>
    <div class="text-yellow-600 font-bold">{{ item.price }}</div>
  </div>
</template>

<script setup>
defineProps(['item'])
</script>
