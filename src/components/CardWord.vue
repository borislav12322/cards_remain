<script setup>

const {cardNumber, word} = defineProps({
  cardNumber: Number,
  word: String,
});

const number = cardNumber < 10 ? `0${cardNumber}` : cardNumber;

</script>

<template>
  <div class="card-word">
    <div class="card-word_wrapper">
      <span class="card-word_number">{{ number }}</span>
      <span class="card-word_word">
        {{ word }}
      </span>

      <button class="card-word_button">
        ПЕРЕВЕНУТЬ
      </button>
    </div>
  </div>
</template>

<style scoped>
.card-word {
  height: 376px;
  width: 250px;
  border-radius: 16px;
  box-shadow: 0 0 16px 0 rgba(0, 0, 0, 0.1);
  background: var(--card-background-color);
  padding: 28px 19px;
}

.card-word_wrapper {
  border: 1px solid var(--border-color);
  border-radius: 12px;
  height: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
  position: relative;
}

.card-word_word {
  font-family: var(--font-family);
  font-weight: 400;
  font-size: 18px;
  text-align: center;
  color: var(--main-font-color);
}

.card-word_number {
  position: absolute;
  top: -10px;
  left: 16px;
  background: var(--card-background-color);
}

.card-word_button {
  cursor: pointer;
  font-family: var(--font-family);
  font-weight: 700;
  font-size: 12px;
  line-height: 150%;
  letter-spacing: 0.12em;
  color: var(--main-header-color);
  background: var(--card-background-color);
  border: none;
  position: absolute;
  bottom: -10px;
  left: 50%;
  transform: translateX(-50%);
}
</style>