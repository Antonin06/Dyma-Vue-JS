<script setup lang="ts">

import {computed, reactive, watch, watchEffect} from "vue";

interface Product {
	name: string
	quantity: number,
	priceHT: number,
	tax: number,
	nbModification: number,
	lastModification?: number | null
}

const product = reactive<Product>({
    name: 'books',
    quantity: 3,
    priceHT: 10,
    tax: 1.2,
		nbModification: 0,
		lastModification: null
})

const totalPriceHT = computed(() => product.quantity * product.priceHT)
const totalPriceTTC = computed(() => product.quantity * product.priceHT * product.tax)

watch(() => product.quantity, (newValue, oldValue) => {
	product.nbModification++;
	console.log(product.nbModification)
})

watchEffect(() => {
	console.log('in watch effect', product.lastModification)
	product.lastModification = Date.now();
	console.log(product.lastModification)
})

</script>

<template>
	<div>
		<input type="number" v-model="product.quantity">
		<div>Prix total HT {{ totalPriceHT }}</div>
		<div>Prix total TTC {{ totalPriceTTC }}</div>
	</div>
</template>

<style scoped>
	div {
		color: red;
	}
</style>