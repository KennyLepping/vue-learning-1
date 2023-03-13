<template>
    <button class="btn">
        <slot>Click me!</slot>
        <!-- slots lets add content to specific component, use this when props
             don't make as much sense - props for more complicated stuff
        -->
    </button>
</template>

<script setup>
// For defining props
// defineProps({
//     text: {
//         type: String,
//         required: false,
//         default: 'Click me!'
//     },
// })
</script>
