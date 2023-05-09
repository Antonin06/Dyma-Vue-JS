<script setup lang="ts">

import FirstSection from "@/components/FirstSection.vue";
import EventPropagation from "@/components/EventPropagation.vue";
import State from "@/components/State.vue";
import Computed from "@/components/Computed.vue";
</script>

<template>
  <section>
    <FirstSection title="Hello VueJS" />
    <EventPropagation />
    <State />
    <Computed />
  </section>
</template>
