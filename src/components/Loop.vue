<script setup lang="ts">
  import {reactive} from "vue";

  const fruits = reactive(['pomme', 'kiwis', 'fraises', 'bananes'])
  const users = reactive([
    {name: 'John', age: 25, status: 'active', notes: ['a', 'b', 'd']},
    {name: 'Jane', age: 24, status: 'inactive', notes: ['a', 'c', 'c']},
    {name: 'Jack', age: 26 , status: 'active', notes: ['a', 'b', 'e']},
  ])
</script>

<template>
    <ul>
        <li v-for="(item, index) in fruits">{{index}}{{item}}</li>
    </ul>
    <ul>
        <li v-for="(user, index) in users">
            <p>{{index}}</p>
            <h3>{{user.name}}</h3>
            <p>{{user.age}}</p>
            <p>{{user.status}}</p>
            <ul>
                <li v-for="(note, index) in user.notes">{{index}}{{note}}</li>
            </ul>
        </li>
    </ul>

    <ul>
        <li v-for="i in 5">{{i}}</li>
    </ul>
</template>

<style scoped>

</style>