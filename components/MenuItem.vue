<template>
  <div class="flex gap-4 bg-white/90 rounded-xl p-4 shadow-md items-center">
    <img :src="item.img" alt="" class="w-16 h-16 rounded-full object-cover border" />
    <div class="flex-1">
      <h3 class="text-base md:text-lg font-semibold">{{ item.name }}</h3>
      <p class="text-xs md:text-sm text-gray-600">{{ item.desc }}</p>
    </div>
    <div class="text-red-700 font-bold text-sm md:text-base">{{ item.price }}</div>
  </div>
</template>

<script setup>
const props = defineProps(['item'])
</script>