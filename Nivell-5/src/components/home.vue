<script setup>
import botones from './botones.vue'
import escenas from './escenas.vue'
import inicio from './inicio.vue'
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

let show= ref(false);
let hide = ref(true);

const empezar = () => {
  show.value = true;
  hide.value = false;
}


</script>

<template>
  <inicio @empezar="empezar()" v-if="hide"/>
  <botones @decrement="decrement()" @increment="increment()" v-if="show"/>
  <escenas v-bind:frases="frases" :current-sentence="currentSentence" v-if="show"/>
</template>

<style scoped>
  
</style>
