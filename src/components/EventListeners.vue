<script setup>
import { ref } from "vue";
const count = ref(0);

function increment() {
  count.value++;
}

function returnZero() {
  count.value = 0;
}
</script>

<template>
  <div>
    <h1>{{ count }}</h1>

    <form @submit=""></form>
    <input @keydown="" />
    <button @click="increment">Increment</button>
    <button @click="returnZero">Go to 0</button>
  </div>
</template>
