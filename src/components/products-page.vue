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

<template>products</template>
