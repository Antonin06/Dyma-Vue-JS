<script setup lang="ts">
import {computed} from "vue";
import type { ProductInterface } from "@/interfaces/product";

const props = defineProps<{
    product: ProductInterface
}>();

const title = computed(() => props.product.name.toUpperCase())
</script>

<template>
    <h2>{{ title }}</h2>
</template>

<style scoped>

</style>