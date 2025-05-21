<template>
  <section>
    <h2 class="text-l md:text-3xl font-bold mb-4 text-center md:text-center text-grey">
      {{ title }}
    </h2>
    <div class="grid gap-4 sm:grid-cols-1 md:grid-cols-2">
      <MenuItem v-for="item in items" :key="item.name" :item="item" />
    </div>
  </section>
</template>

<script setup>
const props = defineProps(['title', 'items'])
</script>
