<script setup>
import Header from "./Header.vue";
import CardWord from "./CardWord.vue";

const word = 'unadmitted';
const number = 1;
</script>

<template>
  <div class="main_content_wrapper">
    <Header/>

    <div class="main_content_box">
      <CardWord :cardNumber="number" :word="word"/>
    </div>
  </div>
</template>

<style scoped>
.main_content_wrapper {
  width: 100%;
  min-height: 100vh;
  display: flex;
  place-items: center;
  flex-direction: column;
}

.main_content_box {
  margin: 0 auto;
  width: 80%;
  height: 500px;
}
</style>
