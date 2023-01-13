<script setup>
  defineProps({
    frases: Array,
  })
</script>

<template>
  <div>
    <ul v-for="frase in frases" class="position">{{ frase }}</ul>
  </div>

</template>

<style scoped>
  .position{
    text-align: center;
    border: 1px solid black;
    border-radius: 25px;
    padding: 1rem;
  }

  @media screen and (max-width: 600px) {
  .position {
    padding: 0.5rem;
  }
}
</style>