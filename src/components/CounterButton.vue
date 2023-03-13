<template>
    <Button
    v-on:mouseover="addOne"
    v-on:click="counter--" 
    id="counter" class="bg-red-700 hover:bg-red-400 rounded-full transition-colors duration-500">
        <slot>Counter: </slot>{{ counter }}
    </Button>
</template>

<script setup>

import Button from './Button.vue'
import { ref } from 'vue'

let counter = ref(0)

const addOne = () => {
    counter.value++
}

</script>