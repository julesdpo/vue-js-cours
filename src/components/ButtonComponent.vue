<template>
    <button 
    :id="data.id"
    :class="data.class ? data.class : ''" 
    :type="data.type ? data.type : 'button'">
    </button>
</template>

<script setup lang="ts">

interface ButtonComponentProperties{
    data:{
        id: string,
        class?: string,
        type?: string,
    }
    
}

defineProps<ButtonComponentProperties>()

</script>