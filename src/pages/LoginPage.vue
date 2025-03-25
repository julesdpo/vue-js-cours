<template>
    <main>
        <h1>Login page</h1>
        <br>
        <FormComponent :data="FormData" @fieldChange="handleFieldChange" />
        <br>
        <p>Pas de compte? Inscrivez vous: </p>
        <router-link to="/register">Register</router-link>
    </main>
</template>

<script setup lang="ts">
import { reactive } from 'vue'
import FormComponent from '../components/FormComponent.vue'
import { useAuthStore } from '../stores/auth-store'
import { storeToRefs } from 'pinia'

const authStore = useAuthStore()
const { getToken } = storeToRefs(authStore)

const finalFormData = reactive({}) as any

const FormData = reactive({
    fields: [
        {
            id: 'email',
            type: 'email',
            placeholder: 'Entrez votre email',
            value: '' // Ajout de la propriété value
        },
        {
            id: 'password',
            type: 'password',
            placeholder: 'Entrez votre mot de passe',
            value: '' // Ajout de la propriété value
        }
    ],
    buttons: [
        {
            id: 'submit-button',
            type: 'submit' as 'submit',
            textContent: 'Valider',
            class: 'is-primary'
        },
        {
            id: 'reset-button',
            type: 'reset' as 'reset',
            textContent: 'Réinitialiser',
            class: 'is-light'
        }
    ]
});

const handleFieldChange = ({ id, value }: { id: string, value: string }) => {
    console.log(`Field changed: ${id} = ${value}`);
    const field = FormData.fields.find(f => f.id === id);
    if (field) {
        field.value = value;
        finalFormData[id] = value;
    }
};

const submitHandler = () => {
        authStore.login(finalFormData)
};

</script>

<style lang="scss">
@import 'bulma';

main {
    padding: 2rem;
}

h1 {
    margin-bottom: 1rem;
}

form {
    max-width: 400px;
    margin: 0 auto;

    label {
        display: block;
        margin-bottom: 0.5rem;
    }

    input {
        margin-bottom: 1rem;
        width: 100%;
    }

    article {
        display: flex;
        justify-content: space-between;
    }

    .validate {
        @extend .button;
        @extend .is-primary;
        margin-right: 1rem;
    }

    .del {
        @extend .button;
        @extend .is-light;
    }
}
</style>
