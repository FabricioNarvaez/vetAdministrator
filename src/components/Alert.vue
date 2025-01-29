<template>
    <div v-if="alert.message" class="alert" :class="alertType">
        {{ alert.message }}
    </div>
</template>

<script setup>
    import { computed } from 'vue';

    const { alert } = defineProps({
        alert: {
            type: Object,
            required: true
        }
    })

    const alertType = computed(() => alert.type);
</script>

<style>
    .alert {
        padding: 1rem;
        margin-top: 1rem;
        border-radius: 0.5rem;
    }

    .error {
        background-color: #f8d7da;
        border-color: #f5c6cb;
        color: #721c24;
    }

    .success {
        background-color: #d4edda;
        border-color: #c3e6cb;
        color: #155724;
    }
</style>