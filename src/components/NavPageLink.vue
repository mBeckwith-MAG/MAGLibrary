<template>
    <div :class="[globalClasses, colorClass]" :activeClass="activeClass">
        <slot></slot>
    </div>
</template>
<script setup>
defineProps({
    colorClass: {
        type: [String, Array],
        default: [
            'bg-stone-100',
            'hover:bg-stone-200',
        ]
    },
    activeClass: {
        type: String,
        default: 'bg-stone-500'
    }
})

const globalClasses = [
    'text-center',
    'uppercase',
    'p-2',
    'cursor-pointer',
    'rounded-b-md',
    'shadow-sm',
    'font-bold',
    'md:rounded-tr-md',
    'md:rounded-bl-none'
]
</script>