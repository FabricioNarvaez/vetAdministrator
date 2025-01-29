<template>
    <div class="form">
        <h2>Crear Seguimiento</h2>
        <form>
            <p>{{ patient.name }}</p>
            <div class="field">
                <label for="name">Nombre Mascota</label>
                <input v-model="patient.name"
                type="text" id="name" placeholder="Nombre de la mascota" />
            </div>
            <div class="field">
                <label for="ownerName">Nombre Propietario/a</label>
                <input v-model="patient.ownerName"
                type="text" id="ownerName" placeholder="Nombre de el/la propietario/a" />
            </div>
            <div class="field">
                <label for="email">Email de contacto</label>
                <input v-model="patient.email"
                type="email" id="email" placeholder="Email" />
            </div>
            <div class="field">
                <label for="admissionDate">Fecha de Alta</label>
                <input v-model="patient.admissionDate"
                type="date" id="admissionDate" />
            </div>
            <div class="field">
                <label for="symptoms">Síntomas</label>
                <textarea v-model="patient.symptoms"
                id="symptoms" placeholder="Describe los síntomas..."/>
            </div>

            <input type="submit" value="Registrar Paciente" class="button" />
        </form>
    </div>
</template>

<script setup>
    import { reactive } from 'vue';

    const patient = reactive({
        name: '',
        ownerName: '',
        email: '',
        admissionDate: '',
        symptoms: ''
    });
</script>

<style>
    @import '@css/Form.css';
</style>