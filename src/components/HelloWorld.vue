<script setup>
import { reactive, ref } from "vue";
const counter = reactive({
  count: 0,
});
console.log(counter.count);
counter.count++;

const message = ref("Hello Composition API");
console.log(message.value);
// message.value = "Changed!!!!!!!";
</script>

<template>
  <h1>Counter</h1>
  <p>{{ counter.count }}</p>

  <h1>Message : {{ message.split(" ").reverse().join("") }}</h1>
</template>

<style scoped></style>
