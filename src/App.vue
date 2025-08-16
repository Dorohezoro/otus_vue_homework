<script setup>
  import ProductList from "./components/ProductList.vue";
</script>

<template>
  <div class="mainContainer" style="font-family: Arial, serif;">
    <span class="heading">Список товаров</span>
    <product-list/>
  </div>
</template>

<style scoped>
  .mainContainer {
    display: flex;
    flex-direction: column
  }

  .heading {
    font-size: 26pt;
    font-weight: bold;
    align-self: center;
  }
</style>
