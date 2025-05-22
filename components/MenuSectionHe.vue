<template>
  <section>
    <h2 class="text-2xl font-bold text-center text-yellow-900 mb-6">{{ title }}</h2>
    <div class="grid gap-4 sm:grid-cols-1 md:grid-cols-2">
      <MenuItemHebrew v-for="item in items" :key="item.name" :item="item" />
    </div>
  </section>
</template>

<script setup>
const props = defineProps(['title', 'items'])
</script>