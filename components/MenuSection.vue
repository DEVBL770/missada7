<template>
  <section class="mb-10">
    <h2 class="text-2xl font-semibold text-gray-800 border-b pb-2 mb-4">{{ title }}</h2>
    <ul class="space-y-4">
      <MenuItem v-for="(item, index) in items" :key="index" :item="item" />
    </ul>
  </section>
</template>

<script setup>
defineProps({
  title: String,
  items: Array
})
import MenuItem from './MenuItem.vue'
</script>
