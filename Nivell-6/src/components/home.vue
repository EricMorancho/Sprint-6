<script setup>
import botones from './botones.vue'
import escenas from './escenas.vue'
import inicio from './inicio.vue'
import { ref } from 'vue'
import { frases } from './arrayEscenas'


let currentSentence = ref(0);
let numberImage = frases[parseInt(currentSentence.value)].img


let imageUrl = ref(new URL('../img/' + numberImage, import.meta.url).href)

const url = () => {
  imageUrl = ref(new URL('../img/' + numberImage, import.meta.url).href)
}

const increment = () => {
  if (currentSentence.value >= 3) {
    currentSentence.value = 3;
  } else {
    currentSentence.value++;
    url();
  }
}

const decrement = () => {
  if (currentSentence.value === 0) {
    currentSentence.value <= 0;
  } else {
    currentSentence.value--
    url();
  }
}

let show = ref(false);
let hide = ref(true);

const empezar = () => {
  show.value = true;
  hide.value = false;
}


</script>

<template>
  <div class="color">

    <img :src="imageUrl" v-if="show" />
    <inicio @empezar="empezar()" v-if="hide" />
    <botones @decrement="decrement()" @increment="increment()" v-if="show" />
    <escenas v-bind:frases="frases" :current-sentence="currentSentence" v-if="show" />

  </div>
</template>

<style>
img {
  position: absolute;
  width: 100%;
  height: 100%;
  z-index: -1;
}
</style>
