<script setup lang="ts">
  import {reactive} from "vue";

  const fruits = reactive(['pomme', 'kiwis', 'fraises', 'bananes'])
</script>

<template>
    <ul v-for="item in fruits">
        <li>{{item}}</li>
    </ul>
</template>

<style scoped>

</style>