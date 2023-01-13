

<script setup>

defineProps({
    frases: Array,
    currentSentence: Number,
})



const emit = defineEmits(["decrement", "increment"]);


</script>

<template>
    <div>

        <button @click="$emit('decrement')" class="boton">Anterior</button>
        <button @click="$emit('increment')" class="boton">Siguiente</button>

    </div>
</template>

<style scoped>
.boton {
    width: 50%;
    font-size: 1.5rem;
    padding: 1rem;
}

@media screen and (max-width: 600px) {
    .boton {
        padding: 0.5rem;
        font-size: 1rem;
    }
}
</style>