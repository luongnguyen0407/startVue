<template>
  <div class="d-flex justify-content-center">
    <button class="btn btn-danger mr-3" @click="handleSelect('NowComponent')">
      danger
    </button>
    <button class="btn btn-success" @click="handleSelect('OldComponent')">
      success
    </button>
  </div>
  <section>
    <keep-alive>
      <component :is="selectComponent" />
    </keep-alive>
  </section>
</template>

<script>
import NowComponent from "./NowComponent.vue";
import OldComponent from "./OldComponent.vue";
export default {
  data() {
    return {
      selectComponent: "NowComponent",
    };
  },
  methods: {
    handleSelect(com) {
      this.selectComponent = com;
    },
  },
  components: {
    NowComponent,
    OldComponent,
  },
};
</script>

<style></style>
