<template>
    <main>
        <input :type= "data.type ? data.type : 'text'"
            :placeholder= data.placeholder 
        />
    </main>
</template>

<script setup lang="ts">

    interface RandomComponentProperties{
        data:{
            type: string,
            placeholder: string,
        }
    }

    defineProps<RandomComponentProperties>()

</script>

