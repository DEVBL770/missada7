<template>
  <li class="flex justify-between items-start border-b pb-3">
    <div>
      <h3 class="text-lg font-medium text-gray-900">{{ item.name }}</h3>
      <p class="text-sm text-gray-600">{{ item.description }}</p>
    </div>
    <div class="text-sm font-semibold text-gray-700 whitespace-nowrap">{{ item.price.toFixed(2) }} €</div>
  </li>
</template>

<script setup>
defineProps({
  item: Object
})
</script>
