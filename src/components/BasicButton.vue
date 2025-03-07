<template>
    <div class="p-4 rounded-md uppercase cursor-pointer font-bold text-center bg-sky-300 hover:bg-sky-400 active:bg-sky-500"
    :class="{'text-white bg-stone-400 hover:bg-stone-500 active:bg-stone-600': darkMode}">
        <slot></slot>
    </div>
</template>
<script setup>
defineProps({
    darkMode: {
        type: Boolean,
        default: false
    }
})
</script>