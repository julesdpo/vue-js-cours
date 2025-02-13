<template>
    <main>
        <h1>Login page</h1>
        <br>
        <FormComponent />
    </main>
</template>

<script setup lang="ts">
import FormComponent from '../components/FormComponent.vue';
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