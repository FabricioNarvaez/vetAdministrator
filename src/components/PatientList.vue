<template>
    <div cla>
        <h2>Lista de Pacientes</h2>
        
        <div v-if="patients.length === 0" class="card">
            <p>No hay pacientes registrados</p>
        </div>
        <div v-else class="card listCard" v-for="patient in patients" :key="patient.name">
            <p>ID: <span>{{ patient.id}}</span></p>
            <p>Nombre: <span>{{ patient.name}}</span></p>
            <p>Propietario: <span>{{ patient.ownerName}}</span></p>
            <p>Email: <span>{{ patient.email}}</span></p>
            <p>Fecha Alta: <span>{{ patient.admissionDate}}</span></p>
            <p>Síntomas: <span>{{ patient.symptoms}}</span></p>
            <div class="listCardActions">
                <button @click="$emit('editPatient', patient)" class="button editButton">Editar</button>
                <button class="button deleteButton">Eliminar</button>
            </div>
        </div>
    </div>
</template>

<script setup>
    defineProps({
        patients: {
            type: Array,
            required: true
        }
    })
    defineEmits(['editPatient']);
</script>

<style>
    @import "@css/PatientList.css";
</style>