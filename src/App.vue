<template>
  <ComponentOne>
    <template v-slot:test>
      <SlotsComponent />
    </template>
  </ComponentOne>
  <DinamicComponent />
</template>

<script>
import ComponentOne from "./components/Props/ComponentOne.vue";
import SlotsComponent from "./components/Slots/SlotsComponent.vue";
import DinamicComponent from "./components/Dinamic/DinamicComponent.vue";
export default {
  name: "App",
  ///context api
  provide() {
    return {
      user: "Hello World",
    };
  },
  components: {
    ComponentOne,
    SlotsComponent,
    DinamicComponent,
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
