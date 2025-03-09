<template>
    <div :class="globalClasses">
        <header :class="[headerClasses, navbarClasses]">
            <div :class="linkClasses">
                <slot name="left-links"></slot>
            </div>
            <div :class="linkClasses">
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
        default: ['bg-stone-200', 'border-stone-300']
    }
})

const globalClasses = [
    'flex',
    'flex-col',
    'gap-1',
    'md:flex-row'
]

const headerClasses = [
    'flex',
    'flex-row',
    'justify-between',
    'gap-1',
    'ps-4',
    'pe-4',
    'pb-4',
    'select-none',
    'border-1',
    'shadow-sm',
    'md:flex-col',
    'md:h-lvh',
    'md:p-0',
    'md:py-4',
    'md:pr-4'
]

const linkClasses = [
    'flex',
    'flex-row',
    'md:flex-col',
    'gap-1'
]
</script>