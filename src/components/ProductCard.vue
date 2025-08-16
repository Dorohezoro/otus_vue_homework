<script setup>
  import ProductCardHeader from "./ProductCardHeader.vue";
  import ProductCardBody from "./ProductCardBody.vue";
  import ProductCardFooter from "./ProductCardFooter.vue";

  defineProps(['product']);
</script>

<template>
  <div class="productCardMainContainer">
    <ProductCardHeader :title="product.title" :category="product.category" style="margin-bottom: 20px"/>
    <ProductCardBody :image="product.image" :price="product.price" :description="product.description" />
    <ProductCardFooter :rating="product.rating" style="margin-top: 20px"/>
  </div>
</template>

<style scoped>
  .productCardMainContainer {
    display: flex;
    border: 5px solid indianred;
    border-radius: 10px;
    margin: 10px;
    flex-direction: column;
    width: 20%;
    flex-wrap: wrap;
    flex-grow: 1;
    justify-content: space-between;
  }
</style>