<template>
  <div v-if="data" class="card text-left">
    <img class="card-img-top" :src="data.src" alt="" />
    <div class="card-body">
      <h4 class="card-title">{{ data.name }}</h4>
      <p class="card-text">{{ user }}</p>
      <button class="btn btn-info" @click="handleClick(data)">Click me</button>
    </div>
  </div>
</template>

<script>
export default {
  methods: {
    handleClick(product) {
      this.$emit("click-custom-event", product);
    },
  },
  //context api
  inject: ["user"],
  props: {
    userClick: Function,
    data: {
      type: Object,
      required: true,
    },
    testProps: {
      type: String,
      default: "ehloo",
    },
  },
};
</script>

<style></style>
