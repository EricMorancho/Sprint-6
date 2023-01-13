<script setup>
defineProps({
    frases: Array,
    currentSentence: Number,
})
</script>

<template>
    <div>
        <ul v-for="(frase, index) in frases" :key="index" :indice="index" id="position"
            :class="{ active: index === currentSentence }">
            {{ frase }}</ul>
    </div>
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
