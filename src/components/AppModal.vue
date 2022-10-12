<template>
  <div v-if="isOpen" class="app_modal" @click="handleCloseModal">
    <div class="modal_container" @click.stop>
      <div class="modal_header">
        <span>Cart</span>
        <i class="fa fa-times" @click="handleCloseModal"></i>
      </div>
      <div class="modal_content mt-2">
        <slot></slot>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    isOpen: {
      type: Boolean,
      default: false,
    },
    handleCloseModal: Function,
  },
  handleOpenModal: Function,
};
</script>

<style scoped>
.app_modal {
  position: fixed;
  inset: 0;
  background-color: rgba(0, 0, 0, 0.4);
}
.modal_container {
  position: absolute;
  padding: 10px;
  background: white;
  border-radius: 12px;
  top: 50%;
  left: 50%;
  width: 60%;
  transform: translate(-50%, -50%);
}
.modal_header {
  display: flex;
  justify-content: space-between;
  align-items: center;
}
.modal_header i:hover {
  background-color: #6a5af9;
  color: white;
  cursor: pointer;
  padding: 3px;
  transition: all 0.25s linear;
  border-radius: 50%;
}
</style>
