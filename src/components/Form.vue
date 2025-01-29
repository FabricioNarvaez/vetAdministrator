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

<style>
    .form {
        display: flex;
        flex-direction: column;
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

    input[type="date"]::-webkit-datetime-edit {
        color: gray;
        opacity: 1;
    }
    
    .field textarea,
    .field input {
        font-family: Arial, Helvetica, sans-serif;
        color: black;
        padding: 0.6em 1em;
        font-size: 1em;
        border-radius: 8px;
        border: 1px solid #c0c0c0;
        margin-top: 0.5em;
        width: 100%;
        background-color: #ffffff;
    }

    .field input[type="text"]:hover{
        cursor: pointer;
    }

    .field input[type="text"]:focus {
        outline: none;
        box-shadow: 0 0 2px #c0c0c0;
    }
</style>