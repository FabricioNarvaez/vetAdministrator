<template>
    <div class="form">
        <h2>Crear Seguimiento</h2>
        <form>
            <div class="field">
                <label for="name">Nombre Mascota</label>
                <input type="text" id="name" placeholder="Nombre de la mascota" />
            </div>
            <div class="field">
                <label for="ownerName">Nombre Propietario/a</label>
                <input type="text" id="ownerName" placeholder="Nombre de el/la propietario/a" />
            </div>
            <div class="field">
                <label for="email">Email de contacto</label>
                <input type="email" id="email" placeholder="Email" />
            </div>
            <div class="field">
                <label for="admissionDate">Fecha de Alta</label>
                <input type="date" id="admissionDate" />
            </div>
            <div class="field">
                <label for="symptoms">Síntomas</label>
                <textarea id="symptoms" placeholder="Describe los síntomas..."/>
            </div>

            <input type="submit" value="Registrar Paciente" class="button" />
        </form>
    </div>
</template>

<script setup>
    import { ref } from 'vue';
</script>

<style>
    @import '@css/Form.css';
</style>