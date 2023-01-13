<script setup>
  defineProps({
    frases: Array,
  })
</script>

<template>
  <div>
    <ul v-for="frase in frases">{{ frase }}</ul>
  </div>

</template>

<style scoped>

</style>