<template>
  <div v-if="data" class="card text-left mb-3">
    <img class="card-img-top" :src="data.image" alt="" />
    <div class="card-body">
      <h4 class="card-title product_name">{{ data.name }}</h4>
      <p class="card-text">{{ data.price }}</p>
    </div>
    <div class="m-2">
      <button class="btn btn-danger mr-2" @click="handleAddCart(data)">
        Add cart
      </button>
      <button class="btn btn-success mr-2">Details</button>
    </div>
  </div>
</template>

<script>
export default {
  inject: ["productCart"],
  props: {
    data: Object,
  },
  methods: {
    handleAddCart(data) {
      const index = this.productCart.findIndex(
        (product) => product.id === data.id
      );
      if (index !== -1) {
        this.productCart[index].amount += 1;
      } else {
        const newData = { ...data, amount: 1 };
        this.productCart.push(newData);
      }
    },
  },
};
</script>

<style>
.product_name {
  font-size: 18px;
  white-space: nowrap;
}
</style>
