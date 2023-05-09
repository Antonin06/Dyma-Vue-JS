<script setup lang="ts">
function userClick(from: string) {
    console.log('click from', from);
}

function formSubmit() {
    console.log('Page non rechargé');
}

function escapeUP() {
    console.log('escape pressed');
}
</script>

<template>
	<div @click="userClick('div')">
		<h2 @click.stop="userClick('h2')">Hello World!</h2>
	</div>
	<form @submit.prevent="formSubmit">
		<button>Submit</button>
	</form>
	<input @keyup.escape="escapeUP">
</template>