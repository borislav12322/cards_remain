<script setup>
</script>

<template>
  <button class="main-button">
    <slot/>
  </button>
</template>

<style scoped>
.main-button {
  border: none;
  border-radius: 100px;
  padding: 16px 10px;
  width: 335px;
  height: 68px;
  background: var(--primary-color);
  transition: background 0.5s ease-in-out;
  font-weight: 400;
  font-size: 24px;
  line-height: 150%;
  text-align: center;
  color: var(--button-font-color);
  font-family: var(--main-font);
  cursor: pointer;
}

.main-button:hover {
  background: var(--hover-color);
}
</style>
