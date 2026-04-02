<script setup>
import Header from "./Header.vue";
import CardWord from "./CardWord.vue";
import {ref} from "vue";


const cardsInfo = ref([{
  number: 1,
  word: 'unadmitted',
  translation: 'не допущенный',
  state: 'closed',
  status: 'pending',
},
  {
    number: 2,
    word: 'auto',
    translation: 'автомобиль',
    state: 'open',
    status: 'pending',
  },
  {
    number: 3,
    word: 'phone',
    translation: 'телефон',
    state: 'open',
    status: 'success',
  },
  {
    number: 4,
    word: 'bag',
    translation: 'сумка',
    state: 'open',
    status: 'fail',
  },
]);

</script>

<template>
  <div class="main_content_wrapper">
    <Header/>

    <div class="main_content_box">
      <CardWord v-for="card in cardsInfo" :key="card.number" :cardNumber="card.number" :word="card.word"
                :cardInfoRef="cardsInfo" :state="card.state" :status="card.status" :translation="card.translation"/>
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
  display: flex;
  gap: 107px;
  flex-wrap: wrap;

}
</style>
