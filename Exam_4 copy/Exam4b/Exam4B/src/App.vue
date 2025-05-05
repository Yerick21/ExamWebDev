<script>
import { RouterLink, RouterView } from "vue-router";
import Nav from "./components/Nav.vue";
export default {
  components: {
    Nav,
  },

  data() {
    return {
      plants: [
        { id: 1, name: "Rose", type: "indoor", inStock: true, price: 20 },
        { id: 2, name: "Tulip", type: "outdoor", inStock: false, price: 15 },
        { id: 3, name: "Daisy", type: "indoor", inStock: true, price: 10 },
        { id: 4, name: "Sunflower", type: "outdoor", inStock: true, price: 25 },
        { id: 5, name: "Lily", type: "indoor", inStock: false, price: 30 },
        { id: 6, name: "Orchid", type: "outdoor", inStock: true, price: 40 },
        { id: 7, name: "Tulip", price: 15, type: "outdoor", inStock: false },
      ],

      filterType: "All",
    };
  },

  methods: {
    handleFilter(type) {
      this.filterType = type;
      console.log(this.filterType);
    },
  },
};
</script>

<template>
  <div>
    <Nav @filter-plants="handleFilter"> </Nav>
    <h1>Plant Store App</h1>
    <router-view :plants="plants" :filterType="filterType" />
  </div>
</template>

<!-- Styles -->
<style></style>
