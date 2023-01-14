<script setup>



const emit = defineEmits(["empezar"]);
</script>

<template>
    <div>
        <h2 class="descripcion">El nostre heroi torna a la carrega! Està surcant l'espai sideral quan una nova aventura
            es creua al seu cami, estas preparat per afrontarla?</h2>

        <div class="center">
            <button @click="$emit('empezar')" class="boton">Empezar</button>
        </div>
    </div>
</template>

<style scoped>
.descripcion {
    text-align: center;
}

.boton {
    font-size: 1.5rem;
    left: 40%;
    width: 19rem;
    height: 6rem;
    background: orange;
    margin-top: 1rem;


}

.center {
    text-align: center;

}
</style>
