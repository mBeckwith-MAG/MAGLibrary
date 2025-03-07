<template>
    <div class="flex flex-col md:flex-row gap-1">
        <header class="flex flex-row justify-between gap-1 p-4 shadow-sm select-none md:flex-col md:h-lvh md:p-2" :class="navbarClasses">
            <div class="flex flex-row md:flex-col gap-1">
                <slot name="left-links"></slot>
            </div>
            <div class="flex flex-row md:flex-col gap-1">
                <slot name="right-links"></slot>
            </div>
        </header>
        <main class="m-4">
            <slot name="content"></slot>
        </main>
    </div>    
</template>
<script setup>
defineProps({
    navbarClasses: {
        type: [String, Array],
        default: 'bg-stone-200'
    }
})
</script>