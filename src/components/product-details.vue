<script setup lang="ts">
const props = defineProps<{
  product: {
    title: string
    description: string
    price: number
  }
}>()
</script>

<template>
  <div class="product-details">
    <h1 class="text-2xl font-bold mb-4">{{ props.product.title }}</h1>
    <img
      src="../assets/product-placeholder.jpg"
      alt="Product image"
      class="w-full h-64 object-cover mb-4 rounded-md"
    />
    <p class="text-gray-700 mb-4">{{ props.product.description }}</p>
    <p class="text-lg font-semibold">${{ props.product.price }}</p>
  </div>
</template>
