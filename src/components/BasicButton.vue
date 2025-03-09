<template>
    <div :class="[globalClasses, colors]" :activeClass="activeClass" >
        <slot></slot>
    </div>
</template>
<script setup>
import { computed } from 'vue'

const props = defineProps({
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

const colors = computed(() => {
    
    return props.colorClass.push(`active:${props.activeClass.value}`)
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