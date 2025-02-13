<template>
    <button 
    :class="data.class" 
    :type="data.type">
    </button>
</template>

<script setup lang="ts">

interface ButtonComponentProperties{
    data;{
        class: string,
        type: string,
    }
    
}

defineProps<ButtonComponentProperties>()

</script>