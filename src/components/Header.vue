<script setup>

import Score from "./Score.vue";
</script>

<template>
  <header class="header">
    <div class="header_wrapper">
      <h1 class="header_main-title">ЗАПОМНИ СЛОВО</h1>

      <Score/>
    </div>
  </header>
</template>

<style scoped>
.header {
  width: 100%;
  height: 121px;
}

.header_wrapper {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 37px 62px 36px 66px;
}

.header_main-title {
  font-weight: 700;
  font-size: 16px;
  line-height: 150%;
  letter-spacing: 0.12em;
  color: var(--main-header-color);
  font-family: var(--main-font);
}
</style>