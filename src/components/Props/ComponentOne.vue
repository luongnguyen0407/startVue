<template>
  <div class="container">
    <div class="row">
      <div v-for="(item, index) in products" :key="index" class="col-sm-3">
        <ProductCard
          :data="item"
          :userClick="handleSelectProduct"
          @click-custom-event="handleSelectProduct"
        />
      </div>
    </div>
    <span><slot name="test"></slot></span>
  </div>
</template>

<script>
import ProductCard from "./ProductCard.vue";
export default {
  methods: {
    handleSelectProduct(data) {
      console.log(data);
    },
  },
  data() {
    return {
      products: [
        {
          name: "Product 1",
          src: "https://plus.unsplash.com/premium_photo-1661963236181-9eb0c8d766e3?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=870&q=80",
        },
        {
          name: "Product 2",
          src: "https://plus.unsplash.com/premium_photo-1661963236181-9eb0c8d766e3?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=870&q=80",
        },
        {
          name: "Product 3",
          src: "https://plus.unsplash.com/premium_photo-1661963236181-9eb0c8d766e3?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=870&q=80",
        },
        {
          name: "Product 4",
          src: "https://plus.unsplash.com/premium_photo-1661963236181-9eb0c8d766e3?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=870&q=80",
        },
      ],
    };
  },
  components: {
    ProductCard,
  },
};
</script>

<style></style>
