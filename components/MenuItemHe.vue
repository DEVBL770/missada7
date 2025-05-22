<!-- MenuItemHebrew.vue -->
<template>
  <div class="bg-white rounded-lg overflow-hidden shadow-md flex flex-col md:flex-row">
    <img :src="item.img" :alt="item.name" class="w-full md:w-32 h-32 object-cover" />
    <div class="p-4 flex flex-col justify-between">
      <div>
        <h3 class="text-lg font-semibold text-yellow-900">{{ item.name }}</h3>
        <p class="text-sm text-gray-600">{{ item.desc }}</p>
      </div>
      <span class="text-yellow-700 font-bold mt-2">{{ item.price }}</span>
    </div>
  </div>
</template>

<script setup>
const props = defineProps({ item: Object })
</script>