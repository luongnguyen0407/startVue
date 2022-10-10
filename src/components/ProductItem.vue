<template>
  <div v-if="data" class="card text-left mb-3">
    <img class="card-img-top" :src="data.image" alt="" />
    <div class="card-body">
      <h4 class="card-title product_name">{{ data.name }}</h4>
      <p class="card-text">{{ data.price }}</p>
    </div>
    <div class="m-2">
      <button class="btn btn-danger mr-2">Add cart</button>
      <button class="btn btn-success mr-2">Details</button>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    data: Object,
  },
};
</script>

<style>
.product_name {
  font-size: 18px;
  white-space: nowrap;
}
</style>
