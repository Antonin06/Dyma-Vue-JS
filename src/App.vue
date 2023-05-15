<script setup lang="ts">

import FirstSection from "@/components/FirstSection.vue";
import EventPropagation from "@/components/EventPropagation.vue";
import State from "@/components/State.vue";
import Computed from "@/components/Computed.vue";
import Style from "@/components/Style.vue";
import Condition from "@/components/Condition.vue";
import Loop from "@/components/Loop.vue";
import VOnceVMemo from "@/components/V-Once-V-Memo.vue";
import Product from "@/components/Product.vue";
import {reactive, ref} from "vue";
import data from './components/utils/FakeData.json';
import type {ProductInterface} from "@/interfaces/product";

const product = reactive<ProductInterface>({
    name: 'MX-5',
    prix: 15000,
    available: true
})
// console.table(data)
</script>

<template>
  <section>

      <Product :product="product"/>
<!--      <VOnceVMemo/>-->
<!--      <Loop />-->
<!--      <Condition/>-->
<!--    <Style />-->
<!--    <FirstSection title="Hello VueJS" />-->
<!--    <EventPropagation />-->
<!--    <State />-->
<!--    <Computed />-->
  </section>
</template>
