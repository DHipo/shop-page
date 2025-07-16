<script setup lang="ts">
import ProductCard from './components/product-card.vue'

const products = Array.from({ length: 10 }, (_, i) => ({
  title: `Product ${i + 1}`,
  description: `Description for product ${i + 1}`,
  price: (i + 1) * 10,
}))
</script>

<template>
  <header class="w-full flex flex-row">
    <div class="flex items-center p-6">
      <img src="./assets/logo.svg" alt="Logo of our shop" class="h-16 w-16" />
    </div>
    <nav class="flex items-center justify-end">
      <ul class="flex h-full w-full gap-10 items-center">
        <li class="mx-4"><a href="#">Home</a></li>
        <li class="mx-4"><a href="#">Products</a></li>
        <li class="mx-4"><a href="#">About</a></li>
        <li class="mx-4"><a href="#">Contact</a></li>
      </ul>
    </nav>
  </header>

  <main class="w-full flex flex-wrap">
    <div
      v-for="product in products"
      :key="product.title"
      class="p-4 w-full sm:w-1/2 md:w-1/3 lg:w-1/4"
    >
      <ProductCard
        :title="product.title"
        :description="product.description"
        :price="product.price"
      />
    </div>
  </main>
</template>

<style scoped></style>
