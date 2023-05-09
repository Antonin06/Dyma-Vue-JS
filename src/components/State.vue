<script setup lang="ts">
import {reactive} from "vue";

const state = reactive({
    user: {
        name: 'Toto',
        age: 18
    },
    count: 0
})
function incrementCount() {
    state.count++;
}
function decreaseCount() {
    state.count--;
}

function toggleUserInfo() {
    user.name = user.name === 'Toto' ? 'Antonin' : 'Toto';
    user.age = user.age === 18 ? 28 : 18;
}

const {user} = state;
</script>

<template>
	<div>Bonjour {{ user.name }} </div>
	<div>Age: {{ user.age }} </div>
  <button @click="toggleUserInfo">Toggle User State</button>
	<div>Count: {{ state.count }}</div>
	<button @click="incrementCount">UP</button>
	<button @click="decreaseCount">Down</button>
</template>

<style scoped>

</style>