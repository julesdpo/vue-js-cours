<template>
    <main>
        <h1>Login page</h1>
        <br>
        <FormComponent :data="FormData" />
    </main>
</template>

<script setup lang="ts">
import { reactive } from 'vue'
import FormComponent from '../components/FormComponent.vue'

const FormData = reactive({
    fields: [
        {
            id: 'email',
            type: 'email',
            placeholder: 'Entrez votre email',
        },
        {
            id: 'password',
            type: 'password',
            placeholder: 'Entrez votre mot de passe',
        }
    ],
    buttons: [
        {
            id: 'submit-button',
            type: 'submit',
            textContent: 'Valider',
            class: 'is-primary'
        },
        {
            id: 'reset-button',
            type: 'reset',
            textContent: 'Réinitialiser',
            class: 'is-light'
        }
    ]
});
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
