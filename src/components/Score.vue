<script setup>
import LikeIcon from "../assets/icons/LikeIcon.vue";

const {scores} = defineProps({
  scores: Number,
})
</script>

<template>
  <div class="score">
    <div class="score_wrapper">
      <span class="score_count">{{ scores }}</span>

      <LikeIcon/>
    </div>
  </div>
</template>

<style scoped>
.score {
  flex-shrink: 0;
  max-width: 110px;
  width: 100%;
  height: 48px;
  border-radius: 36px;
  padding: 12px 24px;
  box-shadow: var(--score-box-shadow);
  background: var(--border-color);
}

.score_wrapper {
  display: flex;
  justify-content: space-between;
  align-items: center;
  height: 100%;
}

.score_count {
  font-family: var(--font-family);
  font-weight: 700;
  font-size: 16px;
  line-height: 150%;
  text-align: center;
  color: var(--primary-color);
}
</style>