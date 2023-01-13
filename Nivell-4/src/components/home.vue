<script setup>
import botones from './botones.vue'
import escenas from './escenas.vue'
import { ref } from 'vue';

const frases = [
  "El nostre heroi estava surant per l'espai sideral quan a la llunyania va albirar una nau espacial",

  "Sentia curiositat per l'interior de la nau i es va posar a inspeccionar-la. Va arribar a una sala amb dues portes.",

  "L'heroi va decidir travessar la porta que el portava a casa",

  "Mentrestant, altres herois no van tenir tanta sort en la seva elecció ..."
];

let currentSentence = ref(0);

const increment = () => {
  if (currentSentence.value >= 3) {
    currentSentence.value = 3;
  } else {
    currentSentence.value++;
  }
}

const decrement = () => {
  if (currentSentence.value === 0) {
    currentSentence.value <= 0;
  } else {
    currentSentence.value--
  }
}


</script>

<template>

  <botones @decrement="decrement()" @increment="increment()" />
  <escenas v-bind:frases="frases" :current-sentence="currentSentence" />
</template>

<style scoped>
#position {
  text-align: center;
  border: 1px solid black;
  border-radius: 25px;
  padding: 1rem;
}

.active {
  background-color: peru;
}

@media screen and (max-width: 600px) {
  .position {
    padding: 0.5rem;
  }
}
</style>
