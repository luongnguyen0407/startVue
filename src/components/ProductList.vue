<template>
  <section class="product-list mt-5">
    <h3 class="text-center text-danger font-weight-bold">List Product</h3>
    <div class="product_wrapper row">
      <div v-for="product in listProduct" :key="product.id" class="col-lg-3">
        <ProductItem :data="product" />
      </div>
    </div>
  </section>
</template>

<script>
import ProductItem from "./ProductItem.vue";
import { listProduct } from "../Data.js";
export default {
  components: {
    ProductItem,
  },
  data() {
    return {
      listProduct,
    };
  },
};
</script>

<style></style>
