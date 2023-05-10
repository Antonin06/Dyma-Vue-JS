<script setup lang="ts">
import {computed, reactive, ref} from "vue";

const h1Class = ref(true);
const input = reactive({
    value: '',
    focus: false,
    touched: false
})

const inputOnGoing = computed(() => input.value.length);
const inputError = computed(() => !input.focus && input.touched && input.value.length < 5);
const inputValid = computed(() => input.touched && !input.focus && !inputError.value);
</script>

<template>
	<h1 class="init-class" v-bind:class="{
    hello: h1Class
  }">Hello Test CSS</h1>



	<button @click="h1Class = !h1Class">Submit</button>
	<input class="input" :class="{
        inputOnGoing,
        inputError,
        inputValid
	}"
  @focus="input.focus=true;input.touched=true"
  @blur="input.focus=false;"
  type="text"
  v-model="input.value">
</template>

<style scoped lang="scss">

.input {
	outline: 0;
	border: 2px solid black;
	border-radius: 4px;
	&.inputOnGoing {
		border-color: blue;
	}
	&.inputError {
		border-color: red;
	}
	&.inputValid {
		border-color: green;
	}
}

.hello {
	color: indianred;
}

</style>