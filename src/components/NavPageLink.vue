<template>
    <RouterLink 
        :to="linkTo" 
        class="text-center uppercase p-2 cursor-pointer rounded-b-md shadow-md font-bold text-white bg-sky-300 hover:bg-sky-400 active:bg-sky-500 md:rounded-tr-md md:rounded-bl-none" 
        activeClass="bg-sky-500"
    >
        <slot></slot>
    </RouterLink>
</template>
<script setup>
defineProps({
    linkTo: {
        type: String,
        required: true
    }
})
</script>