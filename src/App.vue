<template>
    <Header />
    <Form @addPatient="addPatient"
        v-model:name="patient.name"
        v-model:owner-name="patient.ownerName"
        v-model:email="patient.email"
        v-model:admission-date="patient.admissionDate"
        v-model:symptoms="patient.symptoms"
    />
    <PatientList :patients="patients" @editPatient="editPatient" />
</template>

<script setup>
    import Header from '@components/Header.vue';
    import Form from '@components/Form.vue';
    import PatientList from '@components/PatientList.vue';

    import { ref, reactive } from 'vue';
    import { uid } from 'uid';

    const patients = ref([]);

    const patient = reactive({
        id: null,
        name: '',
        ownerName: '',
        email: '',
        admissionDate: '',
        symptoms: ''
    });

    const addPatient = () => {
        if(patient.id){
            const index = patients.value.findIndex(patientItem => patientItem.id === patient.id);
            patients.value[index] = {...patient};
        }else{
            patients.value.push({...patient, id: uid()});
        }

        Object.assign(patient, {
                id: null,
                name: '',
                ownerName: '',
                email: '',
                admissionDate: '',
                symptoms: ''
            });
    };

    const editPatient = (patientToEdit) => {
        Object.assign(patient, patientToEdit);
    };
</script>