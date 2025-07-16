<script setup lang="ts">
import { ref, computed } from 'vue'
import homePage from './components/home-page.vue'
import productDetails from './components/product-details.vue'
import productsPage from './components/products-page.vue'

const routes = {
  '/': homePage,
  '/details': productDetails,
  '/products': productsPage,
}
const currentPath = ref(window.location.pathname)

window.addEventListener('hashchange', () => {
  console.log('Hash changed:', window.location.hash)
  currentPath.value = window.location.hash
})
const currentView = computed(() => {
  if (currentPath.value.slice(1) === '') return routes['/']
  console.log('Current path:', currentPath.value.slice(1))
  return routes[('/' + currentPath.value.slice(1)) as keyof typeof routes]
})

const products = Array.from({ length: 10 }, (_, i) => ({
  title: `Product ${i + 1}`,
  description: `Description for product ${i + 1}`,
  price: (i + 1) * 10,
}))
</script>

<template>
  <header class="w-full flex flex-row max-h-[10vh]">
    <div class="flex items-center p-6">
      <img src="./assets/logo.svg" alt="Logo of our shop" class="h-16 w-16" />
    </div>
    <nav class="flex items-center justify-end">
      <ul class="flex h-full w-full gap-10 items-center">
        <li class="mx-4"><a href="/">Home</a></li>
        <li class="mx-4"><a href="/products">Products</a></li>
        <li class="mx-4"><a href="#">About</a></li>
        <li class="mx-4"><a href="#">Contact</a></li>
      </ul>
    </nav>
  </header>

  <component :is="currentView" :products="products" class="w-full h-full" />
</template>

<style scoped></style>
