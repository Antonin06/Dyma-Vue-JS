<script setup lang="ts">
import {reactive, ref} from "vue";

const state = reactive<any>({})

setTimeout(() => {
    state.user = {
        name: 'Antonin',
        age: 28
    }
},3000)
const input = ref('');
</script>

<template>
	<div v-if="state.user">
		<h1>Profil</h1>
		<ul>
			<li>Name: {{state.user?.name}}</li>
			<li>Age: {{state.user?.age}}</li>
		</ul>
	</div>
  <div v-else>Chargement....</div>

	<input v-model="input" type="text">
	<div v-if="input === 'A'">A</div>
	<div v-else-if="input === 'B'">B</div>
	<div v-else-if="input === 'C'">C</div>
	<div v-else>Autre</div>
</template>

<style scoped>

</style>