<script setup lang="ts">
const props = defineProps<{
  title?: string
  description?: string
  price?: number
}>()
</script>

<template>
  <div
    class="shadow-xl rounded-lg bg-emerald-950 hover:scale-105 hover:shadow-2xl transition-all duration-300"
  >
    <div class="w-full h-48 rounded-t-md overflow-hidden">
      <img
        src="../assets/product-placeholder.jpg"
        alt="Product image"
        class="w-full h-full object-cover"
      />
    </div>
    <div class="p-4 space-y-2">
      <div class="flex flex-row justify-between">
        <h2 class="text-xl font-bold">{{ props.title }}</h2>
        <p class="text-lg font-semibold">${{ props.price }}</p>
      </div>

      <p class="text-gray-600">{{ props.description }}</p>
    </div>
  </div>
</template>
