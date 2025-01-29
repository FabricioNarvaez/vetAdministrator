<template>
    <div cla>
        <h2>Lista de Pacientes</h2>
        
        <div class="card" v-if="patients.length === 0">
            <p>No hay pacientes registrados</p>
        </div>
        <div v-else>
            <p>test</p>
        </div>
    </div>
</template>

<script setup>
    import { ref } from 'vue';

    const patients = ref([]);
</script>