<script setup>
import { ref } from "vue";
import ChildComponent from "./ChildComponent.vue";

const parentMsg = ref("from parent message");
</script>

<template>
  <div>Parent Component</div>
  <ChildComponent>
    <h1>{{ parentMsg }}</h1>
  </ChildComponent>
</template>

<style scoped></style>
