<script setup>
  defineProps(["title", "category"])
</script>

<template>
  <div class="header">
    <span class="title">{{ title }}</span>
    <span class="category">{{ category }}</span>
  </div>
</template>

<style scoped>
  .header {
    padding: 5px;
    display: flex;
    flex-direction: column;
    background-color: indianred
  }

  .title {
    text-align: center;
    font-size: 18pt;
    font-weight: bold;
    margin: 5px;
    color: white;
  }

  .category {
    text-align: center;
    color: bisque;
  }
</style>
