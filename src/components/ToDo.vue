<template>
  <div class="todo-container">
    <input
      v-model="newTodo"
      @keyup.enter="addTodo"
      placeholder="Add a new task"
    />
    <button @click="addTodo">Add</button>

    <ul>
      <li
        v-for="(todo, index) in todos"
        :key="index"
        :class="{ completed: todo.done }"
      >
        <input type="checkbox" v-model="todo.done" />
        <span>{{ todo.text }}</span>
        <button @click="removeTodo(index)">Delete</button>
      </li>
    </ul>
  </div>
</template>

<script setup>
import { ref } from 'vue';

const newTodo = ref('');
const todos = ref([]);

function addTodo() {
  if (newTodo.value.trim() === '') return;
  todos.value.push({ text: newTodo.value, done: false });
  newTodo.value = '';
}

function removeTodo(index) {
  todos.value.splice(index, 1);
}
</script>

<style scoped>
.todo-container {
  max-width: 400px;
  margin: 0 auto;
  text-align: left;
}
input[type='text'] {
  padding: 8px;
  width: 70%;
}
button {
  margin-left: 8px;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  margin-top: 10px;
}
.completed span {
  text-decoration: line-through;
}
</style>
