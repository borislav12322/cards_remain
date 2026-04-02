<script setup>

import {computed, reactive} from "vue";
import AccessSmallIcon from "../assets/icons/AccessSmallIcon.vue";
import DeniedSmallIcon from "../assets/icons/DeniedSmallIcon.vue";
import DeniedLargeIcon from "../assets/icons/DeniedLargeIcon.vue";
import AccessLargeIcon from "../assets/icons/AccessLargeIcon.vue";

const {cardNumber, word, cardInfoRef, state, status, translation} = defineProps({
  cardNumber: Number,
  word: String,
  translation: String,
  state: String,
  status: String,
  cardInfoRef: Array,
});

const number = cardNumber < 10 ? `0${cardNumber}` : cardNumber;

const currentCard = [...cardInfoRef].find(card => card.cardNumber === cardNumber);

const onCardClick = (e) => {
  console.log(e);
  console.log('currentCard', currentCard)
  console.log('cardNumber', cardNumber)
  console.log('cardInfoRef', cardInfoRef)
}


const isPending = status === 'pending';
const isSuccess = status === 'success';
const isFail = status === 'fail';

const isOpen = state === 'open';
const isClosed = state === 'closed';

const getWordContent = () => {
  if (isPending) {
    if (isClosed) {
      return word
    }

    if (isOpen) {
      return translation
    }
  }

  if (isSuccess || isFail) {
    if (isOpen) {
      return translation
    }
  }
}

const wordText = getWordContent();

console.log('wordText', wordText);
console.log('status', status);
console.log('state', state);

console.log('(isFail || isSuccess) && isOpen', (isFail || isSuccess) && isOpen)

</script>

<template>
  <div class="card-word">
    <div class="card-word_wrapper">
      <span class="card-word_number">{{ number }}</span>

      <div v-show="(isFail || isSuccess) && isOpen" class="card-word_icon-status">
        <span v-if="isSuccess">
          <AccessLargeIcon/>
        </span>
        <span v-else>
          <DeniedLargeIcon/>
        </span>
      </div>

      <span class="card-word_word">
        {{ wordText }}
      </span>


      <button v-show="isPending && isClosed" class="card-word_button-closed" @click="onCardClick">
        ПЕРЕВЕРНУТЬ
      </button>

      <div v-show="isPending && isOpen" class="card-word-buttons-opened_wrapper">
        <button class="card-word-buttons-opened_button">
          <DeniedSmallIcon/>
        </button>

        <button class="card-word-buttons-opened_button">
          <AccessSmallIcon/>
        </button>
      </div>

      <button v-show="(isFail || isSuccess) && isOpen" class="card-word_button-closed" @click="onCardClick">
        ЗАВЕРШЕНО
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

.card-word_button-closed {
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

.card-word-buttons-opened_wrapper {
  display: flex;
  gap: 35px;
  padding: 9px;
  position: absolute;
  bottom: -25px;
  background: var(--button-font-color);
}

.card-word-buttons-opened_button {
  border: none;
  background: transparent;
  left: 50%;
  cursor: pointer;
}

.card-word_icon-status {
  background: var(--button-font-color);
  position: absolute;
  top: -20px;
  left: 50%;
  transform: translateX(-50%);
}
</style>