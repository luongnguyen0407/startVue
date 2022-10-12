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
  data() {
    return {
      listProductCart: [],
    };
  },
  components: {
    TheHeader,
    ProductList,
  },
  provide() {
    return {
      productCart: this.listProductCart,
      delProduct: this.delProduct,
    };
  },
  methods: {
    delProduct(product) {
      console.log(this.listProductCart);
      this.listProductCart = this.listProductCart.filter(
        (item) => item.id !== product.id
      );
    },
  },
};
</script>

<style>
*,
*::before,
*::after {
  box-sizing: border-box;
}
* {
  margin: 0;
  padding: 0;
  font: inherit;
}
body {
  line-height: 1.5;
}
img,
picture,
video,
canvas,
svg {
  display: block;
  max-width: 100%;
}
input,
button,
textarea,
select {
  outline: none;
}
p,
h1,
h2,
h3,
h4,
h5,
h6 {
  overflow-wrap: break-word;
}
</style>
