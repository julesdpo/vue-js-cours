<template>
    <form method="post">
        <section>
            <FieldComponent @fieldChange="onFieldChange"
             v-for="(field, index) in data.fields" 
                :key="index" 
                :data="field" />
        </section>
        <br>
        <article>
            <ButtonComponent v-for="(button, index) in data.buttons" 
                :key="index" 
                :data="button" />
        </article>
    </form>
</template>

<script setup lang="ts">
import FieldComponent from './FieldComponent.vue'
import ButtonComponent from './ButtonComponent.vue'

interface FormComponentProperties {
    data: {
        fields: Array<{
            id: string;
            type?: string;
            placeholder: string;
            class?: string;
            value?: string; // Ajout de la propriété value
        }>;
        buttons: Array<{
            id: string;
            type: 'submit' | 'reset' | 'button';
            textContent: string;
            class?: string;
        }>;
    };
}

defineProps<FormComponentProperties>();
const emit = defineEmits(['fieldChange']);

const onFieldChange = ({id, value}:{id: string, value: string}) => {
    console.log("id", id);
    console.log("value", value);
    emit('fieldChange', { id, value });
}

</script>
