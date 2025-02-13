<template>
    <button 
    :id="data.id"
    :class="'button ' + (data.class ? data.class : '')" 
    :type="data.type ? data.type : 'button'"
    > {{ data.textContent }}
    </button>
</template>

<script setup lang="ts">

interface ButtonComponentProperties{
    data:{
        textContent: string,
        id: string,
        class?: string,
        type?: 'submit' | 'reset' | 'button',
    }
    
}

defineProps<ButtonComponentProperties>()

</script>