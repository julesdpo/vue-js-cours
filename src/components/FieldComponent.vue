<template>
    <label v-bind:for="data.id"></label>
    <input 
        v-bind:type="data.type ? data.type : 'text'" 
        v-bind:class="'input ' + data.class ? data.class : ''"
        v-bind:placeholder="data.placeholder"
    />
</template>
<script setup lang="ts">

interface FieldComponentProperties{
    data:{
        id: string,
        type?: string,
        placeholder: string
        class?: string,
    }
}

defineProps<FieldComponentProperties>()

</script>