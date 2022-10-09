<script setup>
import { ref, computed } from "vue";

let id = 0;
let newTodo = ref("");
const hideCompleted = ref(false);

const todos = ref([
  { id: id++, text: "Vue", done: false },
  { id: id++, text: "Composition", done: true },
  { id: id++, text: "API", done: true },
]);

const filteredTodos = computed(() => {
  return hideCompleted.value ? todos.value.filter((t) => !t.done) : todos.value;
});

function addTodo() {
  todos.value.push({ id: id++, text: newTodo.value });
  newTodo.value = "";
}

function removeTodo(todo) {
  todos.value = todos.value.filter((t) => t !== todo);
}

defineExpose({
  id,
  newTodo,
  todos,
  filteredTodos,
  addTodo,
});
</script>

<template>
  {{ hideCompleted }}

  <form @submit.prevent="addTodo">
    <input v-model="newTodo" />
    <button>New Todo</button>
  </form>

  <ul>
    <li v-for="todo in filteredTodos" :key="todo.id">
      <input type="checkbox" v-model="todo.done" />

      <span :class="{ done: todo.done }">
        {{ todo.text }}
      </span>

      <button @click="removeTodo(todo)">Remove</button>
    </li>
  </ul>

  <button @click="hideCompleted = !hideCompleted">
    {{ hideCompleted ? "Show all" : "Hide completed" }}
  </button>
</template>

<style scoped>
.done {
  text-decoration: line-through;
}
</style>
