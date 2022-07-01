<script setup>
import { ref } from "vue";
const awesome = ref(true);

function toggle() {
  awesome.value = !awesome.value;
}

const text = ref("fena değilsadasd");
</script>

<template>
  <div>
    <button @click="toggle">Toggle</button>
    <h1 v-if="awesome">Composition API is AWESOME!!!!</h1>
    <h1 v-else>:((((((((((((</h1>

    <h1>Super Section</h1>
    <p>{{ text }}</p>
    <div v-if="text == 'Super'">Vue süper bi' şeymiş</div>
    <div v-else-if="text == 'Orta'">Vue orta bi' şeymiş</div>
    <div v-else-if="text == 'fena değil'">Fena değilmiş</div>
    <div v-else="">Durum tanımlanamadı!!!!</div>
  </div>
</template>
