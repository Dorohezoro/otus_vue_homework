<script setup>
  defineProps(["rating"])
</script>

<template>
  <div class="footer">
    <img src="../images/rating.png" alt="rating logo" class="img">
    <span class="rate">{{ rating.rate }} </span>
    <span class="count">{{ rating.count }} оценок</span>
  </div>
</template>

<style scoped>
  .footer {
    display: flex;
    flex-direction: row;
    justify-content: center;
    font-weight: bold;
    background-color: indianred;
    padding: 10px
  }

  .img {
    width: 32px;
    height: 32px
  }

  .rate {
    align-self: center;
    margin: 5px;
    font-size: 14pt;
    color: white;
  }

  .count {
    color: bisque;
    align-self: center;
    margin: 5px;
    font-size: 12pt;
  }
</style>