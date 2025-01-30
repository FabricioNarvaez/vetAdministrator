<template>
    <section>
        <h2>Crear Seguimiento</h2>
        <div class="card">
    
            <Alert v-if="alert.message" :alert="alert" />
            <form @submit.prevent="submitForm">
                <div class="field">
                    <label for="name">Nombre Mascota</label>
                    <input @input="$emit('update:name', $event.target.value)" :value="name"
                    type="text" id="name" placeholder="Nombre de la mascota" />
                </div>
                <div class="field">
                    <label for="ownerName">Nombre Propietario/a</label>
                    <input @input="$emit('update:owner-name', $event.target.value)" :value="ownerName"
                    type="text" id="ownerName" placeholder="Nombre de el/la propietario/a" />
                </div>
                <div class="field">
                    <label for="email">Email de contacto</label>
                    <input @input="$emit('update:email', $event.target.value)" :value="email"
                    type="email" id="email" placeholder="Email" />
                </div>
                <div class="field">
                    <label for="admissionDate">Fecha de Alta</label>
                    <input @input="$emit('update:admission-date', $event.target.value)" :value="admissionDate"
                    type="date" id="admissionDate" />
                </div>
                <div class="field">
                    <label for="symptoms">Síntomas</label>
                    <textarea @input="$emit('update:symptoms', $event.target.value)" :value="symptoms"
                    id="symptoms" placeholder="Describe los síntomas..."/>
                </div>
    
                <input type="submit" :value="id ? 'Actualizar Paciente' : 'Registrar Paciente'" class="button" />
            </form>
        </div>
    </section>
</template>

<script setup>
    import { reactive } from 'vue';
    import Alert from './Alert.vue';
    
    const props = defineProps({
        name: String,
        ownerName: String,
        email: String,
        admissionDate: String,
        symptoms: String,
        id: String
    })
    const emit = defineEmits(['addPatient', 'update:name', 'update:owner-name', 'update:email', 'update:admission-date', 'update:symptoms']);

    const alert = reactive({
        message: '',
        type: ''
    });

    const submitForm = () => {
        if(Object.values(props).includes('')){
            alert.message = 'Todos los campos son obligatorios';
            alert.type = 'error';
        }else{
            alert.message = 'Paciente registrado correctamente';
            alert.type = 'success';
            emit('addPatient');
        }
    }

</script>

<style>
    @import '@css/Form.css';
</style>