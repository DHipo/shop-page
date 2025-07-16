<script setup lang="ts">
import ProductCard from './components/product-card.vue'
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

  <main>
    <div v-for="i in 10" :key="i" class="p-4">
      <ProductCard />
    </div>
  </main>
</template>

<style scoped></style>
