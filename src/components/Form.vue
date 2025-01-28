<template>
    <div class="form">
        <h2>Crear Cita</h2>
        <form>
            <div class="field">
                <label for="nombre">Nombre</label>
                <input type="text" id="nombre" placeholder="Nombre del paciente" />
            </div>
        </form>
    </div>
</template>

<style>
    .form {
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: center;
        width: 80%;
        max-width: 100%;
        margin: 0 auto;
        padding: 2rem;
        border-radius: 8px;
        background-color: #ffffff;
        box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
    }
    
    .field {
        display: flex;
        flex-direction: column;
        align-items: flex-start;
        margin: 30px;
    }
    
    .field label {
        font-size: 1.2em;
        font-weight: 500;
    }
    
    .field input[type="text"] {
        padding: 0.6em 1em;
        font-size: 1em;
        border-radius: 8px;
        border: 1px solid #1a1a1a;
        margin-top: 0.5em;
        width: 100%;
    }
</style>