<template>
    <div class="flex flex-center gap-2 items-center">
        <label v-if="label" class="uppercase">
            {{ label }}
        </label>
        <div class="uppercase">
            {{ result }}
        </div>
    </div>
</template>
<script setup>
defineProps({
    label: {
        type: String,
        required: false
    },
    result: {
        type: [String, Number, Boolean],
        required: true
    }
})
</script>