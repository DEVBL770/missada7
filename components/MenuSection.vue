<template>
  <section>
    <h2 class="text-2xl font-bold mb-4">{{ title }}</h2>
    <div class="grid grid-cols-1 sm:grid-cols-2 gap-6">
      <MenuItem v-for="item in items" :key="item.name" :item="item" />
    </div>
  </section>
</template>

<script setup>
import MenuItem from './MenuItem.vue'
defineProps(['title', 'items'])
</script>
