<template>
    <div class="flex flex-center gap-2 items-center">
        <label v-if="label">
            {{ label }}
        </label>
        <input 
            :type="inputType" 
            :placeholder="inputPlaceholder" 
            :value="modelValue" 
            @input="$emit('update:modelValue', $event.target.value)" 
            :class="[globalClasses, borderClass, focusClass]"
        />
    </div>
</template>
<script setup>
import { ref, onBeforeMount } from 'vue'

const props = defineProps({
    label: {
        type: String,
        required: false
    },
    inputType: {
        type: String,
        required: true
    },
    inputPlaceholder: {
        type: String,
        required: true
    },
    modelValue: [String, Number, null],
    borderColor: {
        type: String,
        default: 'stone'
    },
    focusColor: {
        type: String,
        default: 'sky'
    }
})

const borderClass = ref(null)
const focusClass = ref(null)

onBeforeMount(() => {
    switch(props.borderColor) {
        case 'purple': borderClass.value = 'border-purple-300';
        break;
        case 'green': borderClass.value = 'border-emerald-300';
        break;
        case 'red': borderClass.value = 'border-red-500';
        break;
        case 'blue':
        case 'sky': borderClass.value = 'border-sky-300';
        break;
        default: borderClass.value = 'border-stone-300';
        break;
    }
    switch(props.focusColor) {
        case 'purple': focusClass.value = 'focus:border-purple-300';
        break;
        case 'green': focusClass.value = 'focus:border-emerald-300';
        break;
        case 'red': focusClass.value = 'focus:border-red-500';
        break;
        default: focusClass.value = 'focus:border-sky-300';
        break;
    }
})

const globalClasses = [
    "border-2",
    "rounded-md",
    "outline-0",
    "p-2",
    "w-full"
]

const emit = defineEmits(['update:modelValue'])
</script>