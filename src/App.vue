<template>
    <Header />
    <Form 
        v-model:name="patient.name"
        v-model:owner-name="patient.ownerName"
        v-model:email="patient.email"
        v-model:admission-date="patient.admissionDate"
        v-model:symptoms="patient.symptoms"
    />
    <PatientList />
</template>

<script setup>
    import Header from '@components/Header.vue';
    import Form from '@components/Form.vue';
    import PatientList from '@components/PatientList.vue';

    import { ref, reactive } from 'vue';

    const patients = ref([]);

    const patient = reactive({
        name: '',
        ownerName: '',
        email: '',
        admissionDate: '',
        symptoms: ''
    });
</script>

<style>
</style>