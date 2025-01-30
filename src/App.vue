<template>
    <Header />
    <Form @addPatient="addPatient"
        v-model:name="patient.name"
        v-model:owner-name="patient.ownerName"
        v-model:email="patient.email"
        v-model:admission-date="patient.admissionDate"
        v-model:symptoms="patient.symptoms"
        :id="patient.id"
    />
    <PatientList :patients="patients" @editPatient="editPatient" @deletePatient="deletePatient"/>
</template>

<script setup>
    import Header from '@components/Header.vue';
    import Form from '@components/Form.vue';
    import PatientList from '@components/PatientList.vue';

    import { ref, reactive, watch, onMounted } from 'vue';
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

    const deletePatient = (patientToDelete) => {
        patients.value = patients.value.filter(patientItem => patientItem.id !== patientToDelete.id);
    };

    onMounted(() =>{
        const patientsFromLocalStorage = JSON.parse(localStorage.getItem('patients'));
        if(patientsFromLocalStorage){
            patients.value = patientsFromLocalStorage;
        }
    });

    watch(patients, (newPatients) => {
        localStorage.setItem('patients', JSON.stringify(newPatients));
    }, { deep: true });
</script>