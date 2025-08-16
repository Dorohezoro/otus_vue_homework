<script setup>
  defineProps(["image", "description", "price"])
</script>

<template>
  <div class="body">
    <img :src="image" class="img" alt="product image"/>
    <span class="price">{{ price }}$</span>
    <span class="description">{{ description }}</span>
  </div>
</template>

<style scoped>
  .body {
    display: flex;
    flex-direction: column;
  }

  .img {
    width: 140px;
    align-self: center;
    padding: 10px;
    margin-bottom: 20px;
  }

  .description {
    text-align: center;
    padding: 5px;
  }

  .price {
    text-align: center;
    font-weight: bold;
    font-size: 16pt;
    margin-bottom: 20px;
  }
</style>
