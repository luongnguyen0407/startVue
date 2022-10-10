<template>
  <div>{{ ms }}</div>
</template>

<script>
export default {
  data() {
    return {
      msg: "Hello world",
    };
  },
  props: {
    ms: Number,
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped></style>
