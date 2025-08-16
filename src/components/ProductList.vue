<script setup>
  import {reactive} from "vue";
  import ProductCard from "./ProductCard.vue";

  const products = reactive([]);

  getProductsFromExternalPage();

  function getProductsFromExternalPage() {
    fetch("https://fakestoreapi.com/products")
        .then(response => {
          if(!response.ok) {
            throw new Error("Не удалось загрузить список продуктов");
          }
          return response.json()
        })
        .then(json => {
          products.push(...json)
          console.log(products)
        })
        .catch(error => alert(error));
  }
</script>

<template>
  <div class="productListMainContainer" >
    <ProductCard v-for="(product) in products" :product="product"/>
  </div>
</template>

<style scoped>
  .productListMainContainer {
    display: flex;
    border: 2px solid indianred;
    border-radius: 10px;
    margin: 10px;
    flex-direction: row;
    flex-wrap: wrap
  }
</style>