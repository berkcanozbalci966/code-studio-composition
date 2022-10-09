<script setup>
import { ref, onMounted, onUpdated } from "vue";
import Computed from "./Computed.vue";

const pTag = ref(null);
const computedComponent = ref(null);
const counter = ref(0);

onMounted(() => {
  pTag.value.textContent = "Ref power";
  console.log(computedComponent.value.filteredTodos);
});

onUpdated(() => {
  console.log("Counter is changed!!! " + counter.value);
});
</script>

<template>
  <div>
    <p ref="pTag">Life Cycle and Template refs</p>
    <p>{{ counter }}</p>
    <button @click="() => counter++">+</button>
    <Computed ref="computedComponent" />
  </div>
</template>

<style scoped></style>
