<template>
  <div class="flex overflow-x-auto gap-2 px-2 py-3 md:justify-center">
    <button
      v-for="cat in categories"
      :key="cat.name"
      @click="$emit('selectCategory', cat.name)"
      class="px-3 py-1.5 rounded-full text-xs md:text-sm font-medium text-gray-700 bg-white hover:bg-red-100 whitespace-nowrap"
    >
      {{ cat.name }}
    </button>
  </div>
</template>

<script setup>
const props = defineProps(['categories'])
</script>