<template>
    <h1>Hello!</h1>
    <!-- <CounterButton>Current Level: </CounterButton> -->
    <!-- <Button class="bg-green-400 transition-colors duration-200 rounded-2xl" /> -->
    <Button v-for="(name, index) in array" >
        {{ index + 1 }}. {{ name }}
    </Button>
    <br>
    <div class="border w-96 h-96" :style="{ backgroundColor: color }"></div>
    <p>Color: {{  color  }}</p>
    <input type="color" v-model="color"><br>
    <form v-on:submit.prevent="onSubmit">
        <label for="firstName">First name: </label>
        <input class="border border-black" type="text" v-model="firstName"><br>
        <label for="age">Age: </label>
        <input class="border border-black" type="number" v-model="age"><br>
        <Button type="submit">Submit</Button>
    </form>
    <p>Hi my name is {{ firstName }} and I'm {{  age }} years old.</p>
</template>


<script setup>

import Button from './components/Button.vue'
import CounterButton from './components/CounterButton.vue'
import { ref } from 'vue'

let array = ['Walt', 'Hank', 'Jesse']
let color = ref('')

// Form Fields
let firstName = ref('')
let age = ref(0)


const onSubmit = () => {
    let user = {
        firstName: firstName.value,
        age: age.value,
    }
    firstName.value = ''
    age.value = 0
    console.info('Form submitted!')
    console.info(user)
}

</script>