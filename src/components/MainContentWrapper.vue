<script></script>

<template>
  <div class="main_content_wrapper">
    <div class="main_content_box">
      <slot />
    </div>
  </div>
</template>

<style scoped>
.main_content_wrapper {
  width: 100%;
  min-height: 100vh;
  display: flex;
  place-items: center;
}

.main_content_box {
  margin: 0 auto;
  width: 80%;
  height: 500px;
  border: 1px solid #ffffff;
}
</style>
