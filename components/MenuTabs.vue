<template>
  <div class="flex justify-center gap-2 p-4 bg-yellow-100 border-b border-yellow-300">
    <button
      v-for="cat in categories"
      :key="cat.name"
      @click="$emit('selectCategory', cat.name)"
      class="px-4 py-2 text-sm rounded-full border border-yellow-800 bg-white hover:bg-yellow-200 transition-all"
    >
      {{ cat.name }}
    </button>
  </div>
</template>