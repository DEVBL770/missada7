<template>
  <section dir="rtl">
    <h2 class="text-2xl font-bold mb-4 text-right">{{ title }}</h2>
    <div class="grid grid-cols-1 sm:grid-cols-2 gap-6">
      <MenuItemHe v-for="item in items" :key="item.name" :item="item" />
    </div>
  </section>
</template>

<script setup>
import MenuItemHe from './MenuItemHe.vue'
defineProps(['title', 'items'])
</script>
