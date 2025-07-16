<script setup lang="ts">
import productCard from './product-card.vue'

const props = defineProps<{
  products: Array<{
    title: string
    description: string
    price: number
  }>
}>()
</script>

<template>
  <div class="w-full grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 lg:grid-cols-4 gap-6 p-6">
    <productCard
      v-for="product in props.products"
      :key="product.title"
      :title="product.title"
      :description="product.description"
      :price="product.price"
    />
  </div>
</template>
