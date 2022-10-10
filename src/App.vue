<template>
  <header>
    <TheHeader />
  </header>
  <main class="container">
    <ProductList />
  </main>
</template>

<script>
import TheHeader from "./components/TheHeader.vue";
import ProductList from "./components/ProductList.vue";
export default {
  components: {
    TheHeader,
    ProductList,
  },
};
</script>

<style></style>
