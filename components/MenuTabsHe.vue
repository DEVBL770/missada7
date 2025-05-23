<template>
  <div dir="rtl" class="bg-blue-100 p-2 flex justify-center gap-2">
    <button
      v-for="cat in categories"
      :key="cat.name"
      @click="$emit('selectCategory', cat.name)"
      class="px-4 py-2 rounded-full bg-white text-blue-700 font-semibold shadow"
    >
      {{ cat.name }}
    </button>
  </div>
</template>

<script setup>
defineProps(['categories'])
</script>
