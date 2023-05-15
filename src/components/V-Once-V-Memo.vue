<script setup lang="ts">

import {ref} from "vue";

const title = ref('Je suis un titre');
const input = ref('');
</script>

<template>

<!--
  V-Once permet de ne plus ecouter les changements de la variable jusqu'a la fin du cycle de vie du composant
-->
  <h1 v-once>{{ title }}</h1>
	<input v-model="input" type="text">
  <p>{{ input }}</p>

<!--
  V-Memo permet de ne plus ecouter les changements de la variable jusqu'a que la variable change.
  En cas de changement il réévalue toute la zone
-->

  <div v-memo="[title]">
      <p>{{ title }}</p>
      <p>
          <strong>Toto</strong>
      </p>
  </div>
</template>

<style scoped>

</style>