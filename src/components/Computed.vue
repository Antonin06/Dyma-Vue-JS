<script setup lang="ts">

import {computed, reactive} from "vue";

const product = reactive({
    name: 'books',
    quantity: 3,
    priceHT: 10,
    tax: 1.2
})

const totalPriceHT = computed(() => product.quantity * product.priceHT)
const totalPriceTTC = computed(() => product.quantity * product.priceHT * product.tax)

</script>

<template>
	<div>
		<input type="number" v-model="product.quantity">
		<div>Prix total HT {{ totalPriceHT }}</div>
		<div>Prix total TTC {{ totalPriceTTC }}</div>
	</div>
</template>