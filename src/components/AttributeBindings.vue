<script setup>
import { ref } from "vue";

const titleClass = ref("title");
</script>

<template>
  <div>
    <h1 :id="titleClass">I'm title</h1>
  </div>
</template>

<style scoped>
.title {
  color: red;
}

#title {
  color: blue;
}
</style>
