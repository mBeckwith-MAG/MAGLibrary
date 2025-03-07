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
            class="border-2 rounded-md outline-0 p-2 w-full"
            :class="[borderColor, focusColor]"
        />
    </div>
</template>
<script setup>
defineProps({
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
        default: 'border-stone-300'
    },
    focusColor: {
        type: String,
        default: 'focus:border-sky-300'
    }
})
const emit = defineEmits(['update:modelValue'])
</script>