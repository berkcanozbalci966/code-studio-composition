<script setup>
import { ref } from "vue";

let id = 0;
let newTodo = ref("");

const todos = ref([
  { id: id++, text: "Vue" },
  { id: id++, text: "Composition" },
  { id: id++, text: "API" },
]);

function addTodo() {
  todos.value.push({ id: id++, text: newTodo.value });
}

function removeTodo(todo) {
  todos.value = todos.value.filter((t) => t !== todo);
}
</script>

<template>
  <form @submit.prevent="addTodo">
    <input v-model="newTodo" />
    <button>New Todo</button>
  </form>

  <ul>
    <li v-for="todo in todos" :key="todo.id">
      {{ todo.text }}
      <button @click="removeTodo(todo)">Remove</button>
    </li>
  </ul>
</template>
