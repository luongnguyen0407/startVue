<template>
  <button @click="handleOpenModal(true)">Open Modal</button>

  <Teleport to="#mo">
    <div v-if="open" class="modd">
      <p>Hello from the modal!</p>
      <button @click="handleOpenModal(false)">Close</button>
    </div>
  </Teleport>
</template>

<script>
export default {
  data() {
    return {
      open: false,
    };
  },
  methods: {
    handleOpenModal(status) {
      console.log(status);
      this.open = status;
    },
  },
};
</script>

<style>
.modd {
  position: fixed;
  background-color: aqua;
  inset: 0;
}
</style>
