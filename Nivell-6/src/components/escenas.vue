<script setup>
defineProps({
    frases: Array,
    currentSentence: Number,
})
</script>

<template>
    <div class="hola">

        <ul v-for="(frase, index) in frases" :key="index" :indice="index" class="position"
            :class="{ active: index === currentSentence }">
            {{ frase.txt }}</ul>

    </div>
</template>

<style >
.position {
    text-align: center;
    border: 1px solid black;
    border-radius: 25px;
    padding: 1rem;
    background-color: white;
    opacity: 0.7;
}


.active {
    background-color: peru;
    opacity: 1;
}

@media screen and (max-width: 600px) {
    .position {
        padding: 0.5rem;
    }
}
</style>
